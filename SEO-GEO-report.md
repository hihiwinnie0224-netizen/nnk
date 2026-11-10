# New New Bank 單頁 SEO × GEO 優化報告

範圍：僅針對現有頁面 `newnewbank-v2.html` 的 SEO 程式碼與內容。未更動 CSS 視覺、版面、配色與互動功能。
原始版本備份：`newnewbank-v2.original-before-seo.html`

---

## 1. 優化後的 Title

```
聯邦數位銀行 New New Bank｜台幣定儲 2.3%、台幣活儲、美金定存
```
（39 字元，核心詞靠前；各項數字皆與頁面內容一致。）

## 2. 優化後的 Meta Description

```
聯邦數位銀行 New New Bank 優惠：台幣定儲最高 2.3%、台幣活儲新戶 10%、美金定存最高 10%。24 小時線上開戶，免臨櫃，5 分鐘完成申請。
```
（80 字元，接近搜尋結果顯示上限，重點已放前段。）

## 3. 標題層級（H1 / H2 / H3）

本頁為單頁式設計，畫面上的標題是設計文案。為了不改設計，我在每個標題後加上「僅供螢幕閱讀器與搜尋引擎讀取」的短說明（`.sr`，視覺上看不到），內容皆為頁面實際主題。

| 層級 | 畫面看到的 | 補充的隱藏說明 |
|---|---|---|
| H1 | 數位理財 回饋放大 從現在開始 | 聯邦數位銀行 New New Bank： |
| H2 | 抓住它，丟出去。 | 聯邦數位銀行 New New Bank 最新優惠互動區，活動期間 116/1/1–6/30 |
| H2 | 一次看完。 | 10 項聯邦數位銀行 New New Bank 帳戶優惠 |
| H2 | 你放多少，能領多少？ | 台幣定儲、台幣活儲新舊戶利息試算 |
| H2 | 三步，搞定。 | 聯邦數位銀行 New New Bank 線上開戶流程 |
| H2 | 一開戶就有感 | 立即線上開戶 |
| H3 | 存款優惠／投資手續費優惠／回饋・轉帳・活動 | （原本即為可見文字，未更動） |

注意：若你希望完全不使用隱藏文字，可改成直接修改畫面上的標題文案，但那會改變設計。

## 4. 關鍵字策略

**限制說明：** 這個環境無法使用 Google Keyword Planner、Google 搜尋趨勢或 Search Console，因此**沒有搜尋量、競爭度或排名數據，我也沒有編造任何數字**。下列是依頁面內容與常見搜尋說法整理的候選詞，請上線後用 Keyword Planner 與 Search Console 實際驗證。

| 類型 | 候選關鍵字 |
|---|---|
| 核心詞 | 聯邦數位銀行、New New Bank、數位銀行 線上開戶、台幣定存 利率、台幣定儲、美金定存 利率、活儲 利率 |
| 次要詞 | 聯邦銀行 線上開戶、數位帳戶、台股定期定額 手續費、海外ETF 手續費、基金 手續費 0 元、跨行提款 手續費、跨行轉帳 手續費 |
| 長尾詞 | 台幣定存 13 個月 2.3%、新戶 活儲 10% 限額 15 萬、舊戶 活儲 1.5%、美金定存 3 個月 10%、海外股票 手續費 0.45%、聯邦信用卡 自扣 10% 回饋、普發一萬 登記 聯邦 抽獎、MaiCoin 開戶禮 |
| 語意詞／常見問題 | 免臨櫃 開戶、24 小時 線上開戶、5 分鐘 開戶、新資金 定義、新戶 舊戶 差別 |

目前已放進 Title／Description／標題／內文的詞：聯邦數位銀行、New New Bank、台幣定儲、台幣活儲、美金定存、線上開戶、免臨櫃，其餘詞已自然出現在優惠說明內文。

**單頁限制：** 目前只有一個網址，無法「依頁面分配不同關鍵字」。若日後要擴大自然流量，建議為台幣定儲、美金定存、海股／ETF、普發一萬各建獨立頁面（本次依指示未新增）。

## 5. HTML／JavaScript SEO 修改

| 項目 | 修改內容 |
|---|---|
| `<html lang>` | `zh-Hant` → `zh-Hant-TW` |
| Title／Description | 如上，並各自獨立 |
| Meta Robots | `index,follow,max-image-preview:large,max-snippet:-1,max-video-preview:-1` |
| Canonical | `https://newnewbank.com.tw/`（**請確認與實際部署網址一致**） |
| Open Graph／Twitter | og:type、site_name、locale、title、description、url、image、image:alt；twitter:card=summary |
| 圖片 ALT | Logo：`聯邦數位銀行 New New Bank 標誌`（並補上 width／height 避免版面位移） |
| **JS 動態內容改為原始碼輸出** | 原本由 JavaScript 產生的內容，AI 爬蟲多半讀不到，已改成 HTML 直接輸出：H1 文字、「免出門、免臨櫃…」說明文字、10 項優惠卡片、試算區預設文字。JS 只負責動畫與點擊。 |
| 完整優惠辦法 | 點開卡片才看到的完整條件，原本只存在 JS；現在以 `#offerTerms`（`hidden`）輸出在 HTML 中，畫面行為不變，且成為單一資料來源 |
| 無 JS 備援 | 加入 `js` 類別機制：JS 不可用時，內容直接顯示，不會因動畫而隱藏 |
| 語意結構 | 維持 `header／nav／main／section／footer`、單一 H1、H2／H3 階層 |

## 6. Schema.org JSON-LD

已內嵌於 `<head>`（`@graph`，共 5 個節點，皆與頁面實際內容一致）：

- `BankOrCreditUnion`（聯邦銀行：名稱、Logo、地址、客服專線，皆取自頁尾）
- `WebSite`
- `WebPage`（含 `breadcrumb`、`mainEntity`、`dateModified`）
- `BreadcrumbList`（單頁，僅首頁一層）
- `OfferCatalog`：10 筆 `Offer`＋`Service`，含完整條件、`validFrom`／`validThrough`（民國 116/1/1–6/30 → 2027-01-01 至 2027-06-30；台幣活儲 2027-01-21 至 2027-07-20）

**刻意未加入的類型：**
- `FAQPage`：頁面上沒有可見的問答內容，不符合使用條件（且 Google 已限縮此類型的搜尋結果呈現）。
- `Article`、`Product`：此頁不是文章也不是實體商品，加入會與內容不符。
- 評價、評分：頁面沒有，沒有加入。

完整 JSON-LD 請直接看 HTML `<head>` 內的 `<script type="application/ld+json">`。

## 7. llms.txt

見檔案 `llms.txt`（網站基本資訊、內容摘要、10 項優惠與條件、開戶流程、重要連結、資訊來源說明）。內容只使用網頁上已公開的資訊。

## 8. 修改位置與部署方式

1. 以 `newnewbank-v2.html` 取代網站現有頁面檔案（建議保留 `newnewbank-v2.original-before-seo.html` 作為回復用）。
2. 將 `llms.txt` 上傳到網站根目錄，使其可由 `https://newnewbank.com.tw/llms.txt` 開啟。
3. **確認 canonical 與 og:url**：若頁面實際網址不是 `https://newnewbank.com.tw/`，請同步修改這兩處與 JSON-LD 內的網址。
4. 以 Google Search Console 的「網址檢查」測試並請求建立索引。
5. 用 Google Rich Results Test 與 Schema Markup Validator 驗證結構化資料。
6. 建議另外製作 1200×630 的分享圖並替換 og:image / twitter:image（目前暫用官方 Logo，屬新增素材，本次未製作）。
7. 日後更新優惠時，請同步修改三處：HTML 的優惠卡片與 `#offerTerms`、JSON-LD 的 `OfferCatalog`、`llms.txt`。（互動區貼紙的資料在 JS 的 `ITEMS`，也請一併更新。）

## 9. 優化前後差異與檢查結果

| 項目 | 優化前 | 優化後 |
|---|---|---|
| Title | New New Bank \| 一開戶就有感 | 聯邦數位銀行 New New Bank｜台幣定儲 2.3%、台幣活儲、美金定存 |
| Meta Description | 無 | 有（80 字元） |
| Canonical／Robots／OG／Twitter | 無 | 有 |
| JSON-LD | 無 | 5 個節點、10 筆優惠 |
| llms.txt | 無 | 有 |
| H1 在原始碼中的文字 | 空（由 JS 產生） | 有文字 |
| 優惠卡片在原始碼中 | 無（由 JS 產生） | 有（10 項） |
| 完整優惠辦法在原始碼中 | 無 | 有 |
| Logo ALT | `New New Bank` | `聯邦數位銀行 New New Bank 標誌` |

**已做的檢查：**
- 優惠卡片的 DOM 與原本 JS 產生的結果比對，**完全一致**。
- 關閉 JavaScript 後，H1、優惠、開戶流程、試算說明與完整辦法皆可在文字中讀到。
- JSON-LD 可被正確解析，所有 `@id` 引用皆能對應。
- 桌機與手機各自載入：無 JS 錯誤、無橫向捲動；點開優惠視窗、切換新舊戶試算皆正常。
- 靜態區塊（一覽、試算、步驟）與修改前的畫面逐像素比對，差異低於 0.4%（為動畫與顆粒質感造成）。

**未能驗證／限制：**
- 無法連線 Google 工具，**未實際測試 Rich Results、索引狀態或排名**，也無法保證排名結果。
- Logo 圖片是直接連到官網圖檔；預覽環境會擋外部圖片，上線後才會顯示。
- `llms.txt` 是新興作法，各 AI 搜尋工具是否採用並不一致，不保證被引用。
- 本頁所列的優惠條件完全依你提供的資料；若官方公告有調整，需同步更新。
