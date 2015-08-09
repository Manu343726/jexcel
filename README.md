# jexcel
Love Microsoft Excel? Love Java? This is your tool.

## Description

Do you love to work on excel charts, but miss the days you were programming in Java? Don't be sad anymore, with jexcel you can combine both! 

Editing excel spreadsheets was never this easy!

``` java
import jexcel.spreadsheets.tools.*

@jexcel.spreadsheet
class MyFirstSheet extends SpreadSheetTemplate
{
    @jexcel.spreadsheet.management.id
    private int _id;
    
    public static MyFirstSpreadSheet setup()
    {
        return SpreadSheetFactory.New<MyFirstSpreadSheet>(new SpreadSheetName("diego_loves_excel.csv"),
                                                          SpreadSheetFileExtension.Csv,
                                                          new SpreadSheetRows(500),
                                                          new SpreadSheetColumns(20));
    }
    
    @jexcel.spreadsheet.management.id_getter
    public int getId()
    {
        return _id;
    }
    
    @jexcel.spreadsheet.row_getter(name="row")
    public SpreadSheetRow getRow(int i)
    {
        return SpreadSheetManager.getInstance().getGlobalManager().getFromContext(this.getId()).getAs<MyFirstSpreadSheet>().getRow(i);
    }
}
```
