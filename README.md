## Documentation

The `PopupService` service can be used to open three types of modal dialogs: [`Common popup`](#common-popup), [`Alert popup`](#alert-popup), [`Confirm poup`](#confirm-poup).

To create a new popup, you need to provide a config for it. Here is `PopupConfig` description: 
#### PopupConfig 
| Name | Description |
| ------ | ------ |
| name?: `string` | Unique name of popup, if not provided will be used default - `'MNX_POPUP_ID'` |
| size?: `PopupSizeEnum` | The size of the popup, [`PopupSizeEnum`](#popupSizeEnum) has some defined `width`, `height` for each size. If you define `width`, `height` of the popup directly in the popup configuration, then this property can be ignored. |
| title?: `string` | The title of the popup |
| target?: `string or ComponentType<any>` | Popup content can be used some text, which will be automatically translated if for such text is the translation in `locale` file or here can be used `Component` |
| buttons?: `PopupButtonConfig[]` | Config of the buttons which will be displayed on the popup, more details are [`here`](#popupButtonConfig) |
| buttonsContainerClass?: `string` | Container class of the popup buttons |
| width?: `number` | Width of the popup |
| height?: `number` | Height of the popup |
| iconClass?: `string` | Class of the icon which will be displayed near the popup title |
| fullContentWidth?: `boolean` | Whether content should take full width of popup content container |

#### PopupSizeEnum
| Name | Value |
| ------ | ------ |
| small | `width: 300, height: 150` |
| medium | `width: 500, height: 250` |
| large | `width: 700, height: 350` |
| confirm | `width: 600, height: 150` |
 
 #### PopupButtonConfig
 | Name | Description |
| ------ | ------ |
| visibility: `boolean` | Whether button is visible to user |
| label: `string` | Text of the button, will be automatically translated if for such text is the translation in `locale` file |
| class?: `string` | Class of the button |
| value: `string or PopupButtonValueEnum` | Identifier of the button, if the user clicked some button and popup was closed, you will know in the popup result by this `value` which button was clicked. Can be used custom identifier or [`PopupButtonValueEnum`](#popupButtonValueEnum) |
 
 #### PopupButtonValueEnum
| Name | Value |
| ------ | ------ |
| ok | `'OK'` |
| yes | `'YES'` |
| no | `'NO'` |
| close | `'CLOSE'` |

 ---
### Common popup
Popup has a default config:
```
const BASE_POPUP_CONFIG: PopupConfig = {
    name: DEFAULT_POPUP_ID,
    size: PopupSizeEnum.small,
    buttons: []
};
```
A dialog is opened by calling the `openPopup` method with a [`PopupConfig`](#popupConfig) as first argument and optional popupData as second argument. Second argument will be used, only when you use in [`PopupConfig`](#popupConfig) `target` propery as `Component`.

```
const data = new Map<string, any>();
data.set('label', 'Label from popup');
this.popupService.openPopup(BASE_POPUP, data);
```

To get the result of popup call:
```
this.popupService.resultDefault(result => {
    console.log(result);
});
```
---
### Alert popup
Popup has a default config:
```
const ALERT_POPUP_CONFIG: PopupConfig = {
    name: DEFAULT_POPUP_ID,
    size : PopupSizeEnum.small,
    buttons: [{
        visibility: true,
        label: 'OK',
        value: PopupButtonValueEnum.ok,
        class: 'action btn'
    }],
    buttonsContainerClass: 'alert-popup-buttons'
};
```

A dialog is opened by calling the `openAlert` method with a [`PopupConfig`](#popupConfig) as first argument.

```
this.popupService.openAlert(ALERT_POPUP);
this.popupService.resultDefault(result => {
    console.log(result);
});
```

---
### Confirm poup
Popup has a default config:
```
const CONFIRM_POPUP_CONFIG: PopupConfig = {
    name: DEFAULT_POPUP_ID,
    size : PopupSizeEnum.confirm,
    iconClass: 'popup-icon info',
    buttons: [{
        visibility: true,
        label: 'COMMON.BUTTON.CONFIRM',
        value: PopupButtonValueEnum.yes,
        class: 'action btn'
    }, {
        visibility: true,
        label: 'COMMON.BUTTON.CANCEL',
        value: PopupButtonValueEnum.no,
        class: 'additional-action btn'PopupButtonValueEnum
    }],
    buttonsContainerClass: 'confirm-popup-buttons'
};
```

A dialog is opened by calling the `openConfirm` method with a [`PopupConfig`](#popupConfig) as first argument.

```
this.popupService.openConfirm(CONFRIM_POPUP);
this.popupService.resultDefault(result => {
    console.log(result);
});
```
---
