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
  KeyNo, Name, TypeId, AcceptNum, DistrictTeam, Sex, Reason, ReasonType, ReasonTypeName, ReasonRemark, Variety, Build, Age, AgeName, Age2, Coat, HairType, Collar, CollarRemark, Thoracodorsal, ThoracodorsalRemark, Adoption, NotAdoption, Situation, SituationName, Situation2, ChipNum, DoglicenseNum, Remark, CreateTime, IsDelete, EscapeDate, EscapeRemark, Status, Address, IsSterilization, SterilizationDate, IsTNR, EarNote, DoctorId, OpenAdoptionTime, ShapeRemark, Story, IsIsolation, IsolationDate, IsolationReason, IsolationRemark, IsQuarantine, QuarantineDate, QuarantineReason, QuarantineRemark, VolunteerAlbum, Note, Resettlement, ChildreAnlong, AnimalAnlong, Phone, Email, AndroidCount, MovieUrl, IsChoice, isInto, SyncTime, CreateUser, UpdateUser, UpdateTime, LengthCoat, DoglicenseDate, DoglicensNoUseId, CageTypeName, CageName, TypeRemark, HealthStatus, HealthStatusRemark, BehaviorRemark, CageIdStr, CageTypeIdStr, MedicineName, VaccineDate, whVariety, WhInto, SearchKeyword, Unit, ShelterName, UserTag, VillageID, VillageName, ErrorMessage, Language, PageSize, CurrentPage, SortFields, SortDirection, RowCount
  
- NotAdoptionName有標注的欄位都刪掉{'健康不適', '年紀不適', '行為不適', '動保案件'}，因為有標註表示他不能被領養
- SituationRemark有標注的欄位都刪掉{'鐘文虎領回', '5/19死亡送回', '5/4自然死亡', '不吃，流濃稠口水，流鼻涕', '8/15由拾獲人帶出', '9/29中途認養'} //但有蠻多中途認養的...
