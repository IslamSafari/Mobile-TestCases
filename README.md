# Mobile-TestCases
In this Blog I have Made 4 Test cases using Appium - TestNG - Maven
First We will need to add all required dependencies for the Maven into The POM.XML File
Then we will need to use a simulator to be able to select Elements in my case I've used Appium Studio
Then we will need to set the device in eclipse and set DesiredCapabilities

Then The 4 cases As Follow 

1-TC for Successfull Registration then assertion

2-TC for Pop up messages

3-TC to be sure Progress par id working well and direct to reg page

4-Finally TC to Check for The Temp text shown when click on a button

Note That for the first case we could use the below code and dependency to read the data from excel sheet

import java.io.FileInputStream;
import java.io.FileNotFoundException;
import java.io.IOException;

import org.apache.poi.xssf.usermodel.XSSFCell;
import org.apache.poi.xssf.usermodel.XSSFRow;
import org.apache.poi.xssf.usermodel.XSSFSheet;
import org.apache.poi.xssf.usermodel.XSSFWorkbook;
import org.apache.poi.util.POILogger;
import org.apache.poi.openxml4j.opc.PackageRelationshipCollection;
public class ExcelDriven {
public static XSSFWorkbook wb; 
public static XSSFSheet sheet;
public static XSSFRow row;
public static XSSFCell cell;
public static FileInputStream fis;

public static void main(String[] args) throws IOException {
    // TODO Auto-generated method stub
//   fis = new FileInputStream("/Users/tabish/Downloads/data.xlsx");    

}
public static String getCellData(int rownum,int col, String fileName)
{
     try {
         fis = new FileInputStream("/path/to/file/"+fileName+".xlsx");
         wb = new XSSFWorkbook(fis);
         sheet= wb.getSheet("Sheet1");
         row = sheet.getRow(rownum);
         cell = row.getCell(col);
    //   System.out.println(cell.getStringCellValue());
         if (cell==null){
             return "";
         }
         return cell.getStringCellValue();

    } 
     catch (Exception e)
     {
        System.out.println("In the Catch Block:"+e);
         return "Exception Occured";
    }

} 




<dependency>
        <groupId>org.apache.poi</groupId>
        <artifactId>poi-ooxml</artifactId>
        <version>3.13</version>
</dependency>
