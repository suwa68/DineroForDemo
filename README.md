# dineroSpringBoot

以下是陳革維負責的部分
#標題為 pacakge 名稱
##標題為class及interface
部分包含檔案描述
此外有標註覺得較值得討論的內容

---



# com.dinero.config


## AuthMemmerSuccessHandler

在user 登入時 與database互動
取得Princiapal 物件未包含的 userid

## SessionConfig

從外部綠界跳轉回來時session 
之購物車不被清掉

---




# com.dinero.controller

## CartController

使用者將商品新增至購物車之跳轉
包含存貨控制
由於是課程中期寫出來的
應該要將當中的 商業邏輯交給 service 層
單純負責跳轉就好

## CartServerSideController

管理者管控訂單與訂單明細之controller
有實行抽象化分層 
service中的邏輯就想在service裡

## CoupunController

以及優惠券增刪改查
包含所有套用優惠券時使用的ajax端點

---




# com.dinero.util

## CartExcelExporter

有使用泛型
能幫助 訂單 及 優惠券 匯出excel 檔

## DateTransformer

將所有的日期轉換method定義在此 class中

## DineroExceptnion

自訂的 runtimException
會由 @ControllerAdvice
NotLogInExceptionHandler 處裡

---




# com.dinero.model

## CouponBean

參考 oracle 工程師提供的資料設計

## CpuponService 
中包含了套用優惠券時的邏輯

## CouponRespository

當中有判斷新增優惠券時
該時間堅區段內存在之優惠券

## CartDao
使用了 stream api 用 .filter 對多條件搜尋
現在來看寫在 service 會更好

DiscountType(Enum)
CartBean
CartItemBean
CartItemDao
CartItemService
CartService
GeProductBean
GeProductDao
GeProductService
ICartDao
ICartItemDao
ICartItemService
ICartService
ICartService
IGeProductService
OrderStatus(Enum)

# src/main/webapp/gewei

為份量不少的jsp
採model2
其中 
cartoutcome.jsp
createCOupon.jsp 寫了不少非同步
當然另外抽出來js檔較佳
