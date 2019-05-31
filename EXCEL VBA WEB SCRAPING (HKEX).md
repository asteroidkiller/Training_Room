# EXCEL VBA WEB SCRAPING (HKEX)
----

### DAILY MARKET REPORT _After-Hours Trading Session_

港交所夜期資料示範 [(港交所網站資料位置)](<https://www.hkex.com.hk/Market-Data/Statistics/Derivatives-Market/Daily-Market-Report-(Latest)?sc_lang=en>)

因為工作需要, 需要抓取以下港交所部份期貨/期權T+1_**合約總成交數**_ (須按以下排列次序)

1. [Hang Seng Index Futures](https://www.hkex.com.hk/eng/stat/dmstat/dayrpt/dmreport1.htm)

2. [Hang Seng China Enterprises Index Futures](https://www.hkex.com.hk/eng/stat/dmstat/dayrpt/dmreport3.htm)

3. [Mini-Hang Seng Index Futures](https://www.hkex.com.hk/eng/stat/dmstat/dayrpt/dmreport2.htm)

4. [Mini-Hang Seng China Enterprises Index Futures](https://www.hkex.com.hk/eng/stat/dmstat/dayrpt/dmreport14.htm)

5. [USD/CNH Futures](https://www.hkex.com.hk/eng/stat/dmstat/dayrpt/dmreport26.htm)

6. [Hang Seng Index Options](https://www.hkex.com.hk/eng/stat/dmstat/dayrpt/dmreport8.htm)

7. [Hang Seng China Enterprises Index Options](https://www.hkex.com.hk/eng/stat/dmstat/dayrpt/dmreport10.htm)

8. [Mini-Hang Seng Index Options](https://www.hkex.com.hk/eng/stat/dmstat/dayrpt/dmreport9.htm)

9. [Mini-Hang Seng China Enterprises Index Options](https://www.hkex.com.hk/eng/stat/dmstat/dayrpt/dmreport15.htm)

   

```
Sub checkresult()

On Error Resume Next

[A5].CurrentRegion.Clear
ActiveSheet.Rows.RowHeight = 15

Dim mydate As Double
mydate = [A2]

Dim i As Integer
Dim products(4) As String

products(0) = "hsi"
products(1) = "hhi"
products(2) = "mhi"
products(3) = "mch"
products(4) = "cus"

i = 5
For Each myproduct In products

Dim myxml As Object
Set myxml = CreateObject("Microsoft.xmlhttp")
With myxml
    .Open "get", "https://www.hkex.com.hk/eng/stat/dmstat/dayrpt/" & myproduct & "fa" & mydate & ".htm", False
    .send
    text0 = .responsetext
End With
text1 = Split(text0, "omissions.")(1)
text2 = Split(text1, "Contract         STRATEGY")(0)
text3 = Split(text2, "After-Hours")(0)
text4 = Split(text3, "Business Day")(0)
Cells(i, 2) = Replace(Split(text4, " HK$")(0), " RMB10 per minimum fluctuation", "")
Cells(i, 2) = Replace(Cells(i, 2), "Contract Size = USD$100,000", "")
Cells(i, 3) = Replace(Split(text3, " Day")(1), " ", "")
text4 = Split(text2, "After-Hours")(1)
Cells(i, 1) = Replace(Split(text4, "All Contracts Total")(1), " ", "")

Cells(i, 1).ColumnWidth = 7.4
Cells(i, 2).ColumnWidth = 52.3
Cells(i, 3).ColumnWidth = 23.8
[A5].CurrentRegion.Select

Selection.WrapText = False

i = i + 1

Next

Dim op(3) As String

op(0) = "hsio"
op(1) = "hhio"
op(2) = "mhio"
op(3) = "mcho"

For Each myop In op

Dim myxml2 As Object
Set myxml2 = CreateObject("Microsoft.xmlhttp")
With myxml2
    .Open "get", "https://www.hkex.com.hk/eng/stat/dmstat/dayrpt/" & myop & "a" & mydate & ".htm", False
    .send
    op0 = .responsetext
End With
op1 = Split(op0, "omissions.")(1)
op2 = Split(op1, "After-Hours")(0)
Cells(i, 2) = Replace(Split(op2, " HK$")(0), " ", "")
Cells(i, 3) = Replace(Split(op2, " Day")(1), " ", "")
op3 = Split(op1, "MARKET")(1)
op4 = Split(op3, "After-Hours")(0)
Cells(i, 1) = Replace(Split(op4, "***  E")(0), " ", "")
Cells(i, 1) = Replace(Cells(i, 1), "TOTAL", "")

[A5].CurrentRegion.Select
Selection.WrapText = False

i = i + 1

Next

ActiveSheet.Range("A2").Select

Set myxml = Nothing
Set myxml2 = Nothing

End Sub
```

執行按鈕BUTTOM

BUTTOM CAPTION: 查詢網站資料

```
Private Sub CommandButton1_Click()
Call checkresult
End Sub
```



### **遺留問題:**

-儲存格仍有空格行, 無法以REPLACE方法去除

-內容太太太冗長
