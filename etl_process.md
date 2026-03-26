# Data tabel preparation for PowerBI

### **FactGame**

AppID (FK → DimGame)  
GenreID (FK → DimGenre)  
DateID (FK → DimDate)  
Price_USD  
Discount_Pct  
Review_Score_Pct  
Total_Reviews  
Estimated_Owners  
24h_Peak_Players  


### **DimGame**
  
AppID (PK)  
Name  
Steam_Deck_Status  

### **DimGenre**
  
GenreID (PK)  
GenreName  

### **DimDate**
  
DateID (PK)  
Date  
Year  
Month  
Quarter  
