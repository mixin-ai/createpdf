
<img width="629" height="709" alt="image" src="https://github.com/user-attachments/assets/b81b564f-c872-4979-9209-2e42d2621a4e" />
```java
              //使用
           // 创建检验报告数据
            InspectionReportData inspectionReportData = createTestInspectionData();
            // 生成PDF报告
            String outputPath = name+".pdf";
            File targetFile = new File("/xxx/" + outputPath);
            CreatePDF.generateReport(inspectionReportData,"testRecord.ftl" ,targetFile);

```

```java
private InspectionReportData createTestInspectionData() {
        InspectionReportData reportData = new InspectionReportData();
        
        // 设置基本信息
        reportData.setClient("北京某制药有限公司");
        reportData.setOrderNumber("ORD-2024-TEST-001");
        reportData.setLevel("合格品");
        reportData.setBatchNumber("20240115");
        reportData.setTestNumber("TEST-2024-WEB-001");
        reportData.setSendTime("2024-01-15");
        reportData.setQrCode("base64编码图片");
        reportData.setItemCount("4");
        reportData.setReceiver("张三");
        reportData.setPrintPerson("李四");
        reportData.setMethodRecordTitle("");
        reportData.setMethodRecord("按照《中国药典》2020年版相关标准进                      行检验，严格按照SOP操作 "+reportData.nextLine()+"(1).asdfasdf");
        reportData.setMethodResult("所检项目均符合标准要求，产品质量合格");
        
        // 创建检项列表
        List<InspectionItem> items = new ArrayList<>();
        
        items.add(new InspectionItem(
            "性状", 
            "胶囊剂应符合胶囊剂项下的有关规定胶囊剂应符合胶囊剂项下的有关规定胶囊剂应符合胶囊剂项下的有关规定",
            "符合规定", 
            "外观完整，无破损，颜色正常", 
            "0.5h"
        ));
        
        items.add(new InspectionItem(
            "鉴别", 
            "应显相同的颜色反应", 
            "符合规定", 
            "显紫红色反应", 
            "1.0h"
        ));
        
        items.add(new InspectionItem(
            "检查-水分", 
            "不得过5.0%", 
            "3.1%", 
            "符合标准要求", 
            "2.0h"
        ));
        
        items.add(new InspectionItem(
            "含量测定", 
            "标示量的90.0%~110.0%", 
            "99.2%", 
            "含量合格", 
            "3.0h"
        ));
        
        reportData.setItems(items);
        
        return reportData;
    }
```
