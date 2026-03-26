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
  
AppID (PK)  
GenreName  

### **DimDate**
  
DateID (PK)  
Date  
Year  
Month  
Quarter  


### SQL Queries  
CREATE TABLE FactSteam AS  
  SELECT AppID, Release_Date, Price_USD, Discount_Pct, Review_Score_Pct, Total_Reviews, Estimated_Owners, "24h_Peak_Players" AS Peak_Players_24h  
FROM steam_games_2026  
  
CREATE TABLE DimSteamName AS   
  SELECT AppID, Name, Steam_Deck_Status, Primary_Genre, All_Tags  
FROM steam_games_2026  


