# ColumnTable

A react component for creating tables configured by a set of columns.

## Set up
1. Install dependencies with `npm install`

## Building
1. To build files for production, run `grunt deploy`


# Features Roadmap

- [ ] sort
- [ ] column hover
- [x] th classes
- [x] td classes
- [ ] fixed widths
- [x] striping
- [x] anything as a th (component, string)
- [ ] formatting
- [ ] highlighting a max or min value
- [ ] value, sort value, render
- [ ] column grouping
- [ ] group headers
- [ ] repeat headers every N

## Stretch features
- [ ] loading view
- [ ] selecting rows
- [ ] fixed headers
- [ ] fixed columns
- [ ] CSV export
- [ ] heatmap
- [ ] paging
- [ ] showing row numbers on hover
- [ ] ImmutableJS support?
- [ ] hiding rows below threshold
- [ ] hiding cells below threshold
- [ ] expandable rows?


# Columns

Columns should support the following properties.

Here `Renderable` means anything React can render (e.g., React.Component, String, etc.).


| Property | Type | Required | Description |
| -------- | ---- | -------- | ----------- |
| id | String | Yes | The id of the column. Typically corresponds to a key in the rowData object. |
| className | String |  | The class name to be applied to both `<td>` and `<th>` |
| firstSortDirection | Boolean |  | The direction which this column gets sorted by on first click |
| header | Renderable |  | What is rendered in the column header. If not provided, uses the columnId. |
| highlight | Function |  | `function (cellData, columnSummary, columnDefinition, rowData, rowNumber, tableData, columnsDefinition)`<br>A function that returns a boolean indicating whether or not to highlight the cell. |
| renderer | Function |  | `function (cellData, columnDefinition, rowData, rowNumber, tableData, columnsDefinition)`<br>The function that renders the value in the table. Can return anything React can render. |
| rendererOptions | Object |  | Object of options that can be read by the renderer |
| simpleRenderer | Function |  | `function (cellData, columnDefinition, rowData, rowNumber, tableData, columnsDefinition)`<br>The function that render the cell's value in a simpler format. Must return a String or Number. |
| sortValue | Function |  | `function (cellData, rowData)`<br>Function to use when sorting instead of `value`. |
| tdClassName | String |  | The class name to be applied to `<td>` only |
| thClassName | String |  | The class name to be applied to `<th>` only |
| type | String |  | The `DataType` of the column - number, string, etc |
| value | String, Function |  | `function (rowData, rowNumber, tableData, columnsDefinition)`<br>Function to produce cellData's value. If a String, reads that as a key into the rowData object. If not provided, columnId is used as a key into the rowData object. |
| width | String, Number |  | The value to set for the style `width` property on the column. |



