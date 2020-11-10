## Documentation

The `PopupService` service can be used to open three types of modal dialogs: [`Common popup`](#common-popup), `Alert popup`, `Confirm poup`.

#### Properties

| Name | Description |
| ------ | ------ |
| @Input() id: string | `id` of Datepicker, if not provided, will be generated automatically from the `label` value |
| @Input() label: string | `label` of Datepicker, also used for generating `id` if it's not provided |
| @Input() selectedDate: Moment | Default selected date |
| @Input() monthYearMode: boolean | Whether have the ability to select only month and year in Datepicker |
| @Input() format: string | Format of date displayed in Datepicker |
| @Input() skipWeekends: boolean | Whether disable weekends and have the ability to select only working days |
| @Input() minAllowedValue: Moment | Min allowed date to select in Datepicker |
| @Input() maxAllowedValue: Moment | Max allowed date to select in Datepicker |
| @Input() disabledValues: Moment[] | Dates which are disabled in Datepicker |
| @Input() enabledValues: Moment[] | Dates which are enabled in Datepicker, all others will be disabled |
| @Input() todayFormat: string | Format of displayed today day in Datepicker |
| @Output() dateChange = new EventEmitter<Moment>() | Listen on date changes |
#### Properties

| Name | Description |
| ------ | ------ |
| @Input() id: string | `id` of Datepicker, if not provided, will be generated automatically from the `label` value |
| @Input() label: string | `label` of Datepicker, also used for generating `id` if it's not provided |
| @Input() selectedDate: Moment | Default selected date |
| @Input() monthYearMode: boolean | Whether have the ability to select only month and year in Datepicker |
| @Input() format: string | Format of date displayed in Datepicker |
| @Input() skipWeekends: boolean | Whether disable weekends and have the ability to select only working days |
| @Input() minAllowedValue: Moment | Min allowed date to select in Datepicker |
| @Input() maxAllowedValue: Moment | Max allowed date to select in Datepicker |
| @Input() disabledValues: Moment[] | Dates which are disabled in Datepicker |
| @Input() enabledValues: Moment[] | Dates which are enabled in Datepicker, all others will be disabled |
| @Input() todayFormat: string | Format of displayed today day in Datepicker |
| @Output() dateChange = new EventEmitter<Moment>() | Listen on date changes |
 
### Common popup

#### Properties

| Name | Description |
| ------ | ------ |
| @Input() id: string | `id` of Datepicker, if not provided, will be generated automatically from the `label` value |
| @Input() label: string | `label` of Datepicker, also used for generating `id` if it's not provided |
| @Input() selectedDate: Moment | Default selected date |
| @Input() monthYearMode: boolean | Whether have the ability to select only month and year in Datepicker |
| @Input() format: string | Format of date displayed in Datepicker |
| @Input() skipWeekends: boolean | Whether disable weekends and have the ability to select only working days |
| @Input() minAllowedValue: Moment | Min allowed date to select in Datepicker |
| @Input() maxAllowedValue: Moment | Max allowed date to select in Datepicker |
| @Input() disabledValues: Moment[] | Dates which are disabled in Datepicker |
| @Input() enabledValues: Moment[] | Dates which are enabled in Datepicker, all others will be disabled |
| @Input() todayFormat: string | Format of displayed today day in Datepicker |
| @Output() dateChange = new EventEmitter<Moment>() | Listen on date changes |
