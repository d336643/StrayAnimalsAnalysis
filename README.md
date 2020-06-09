# StrayAnimalsAnalysis
 台灣流浪動物滯留收容所天數預測系統
 
### 原始資料及描述：

### 處理完資料：clean.csv
##### clean1.csv
- 許多 cell 都是 na，但如果移掉這些資料最後會全清掉，目前是把na都改成”無“
- Bodyweight: {NaN, 13\~15, 2公斤, 4...} => {無, 5\~10, 0\~5, 10\~15, 15\~20, 20以上}
- Coat 系列皆用人工挑選出大類，無法分類則寫「其他」，未填寫寫「無」
  - ex. FootCoat :{'1腳受傷', '前腳腳趾前端有白毛','左前肢 橈骨脫臼，尺骨近端斷裂。',...} => {黃95, 無106330, 白319, 其他180, 受傷41, 虎斑78, 棕灰黑45}
  - 但這種分法可能導致某些種類個數太少，其他跟無太多
- 移除欄位：
  Name, TypeId, AcceptNum, DistrictTeam, Sex, Reason, ReasonType, ReasonTypeName, ReasonRemark, Variety, Build, Age, AgeName, Age2, Coat, HairType, Collar, CollarRemark, Thoracodorsal, ThoracodorsalRemark, Adoption, NotAdoption, Situation, SituationName, Situation2, ChipNum, DoglicenseNum, Remark, CreateTime, IsDelete, EscapeDate, EscapeRemark, Status, Address, IsSterilization, SterilizationDate, IsTNR, EarNote, DoctorId, OpenAdoptionTime, ShapeRemark, Story, IsIsolation, IsolationDate, IsolationReason, IsolationRemark, IsQuarantine, QuarantineDate, QuarantineReason, QuarantineRemark, VolunteerAlbum, Note, Resettlement, ChildreAnlong, AnimalAnlong, Phone, Email, AndroidCount, MovieUrl, IsChoice, isInto, SyncTime, CreateUser, UpdateUser, UpdateTime, LengthCoat, DoglicenseDate, DoglicensNoUseId, CageTypeName, CageName, TypeRemark, HealthStatus, HealthStatusRemark, BehaviorRemark, CageIdStr, CageTypeIdStr, MedicineName, VaccineDate, whVariety, WhInto, SearchKeyword, Unit, UserTag, VillageID, VillageName, ErrorMessage, Language, PageSize, CurrentPage, SortFields, SortDirection, RowCountSituationRemark
  
- NotAdoptionName 欄位留著，{'健康不適', '年紀不適', '行為不適', '動保案件'}


##### clean2.csv
- 把 Coat系列欄位統整特徵欄位【黃、棕、灰、黑、白、橘、虎斑、受傷（生病）、麒麟尾、剪耳、四眼、截尾】
  - 這其實是人工篩選出來的特徵...
- 把重量改成 continuous instead of category
- 新增認養欄位

