# Google-cloud-study-obtain-monthly-subscription

## 第一步透過下方連結報名Google cloud study2022的活動

[Google cloud study2022報名連結](https://docs.google.com/forms/d/e/1FAIpQLScTpsT49MGBiJ_pNPYGJvvUBE90mXxsDmJSRFlFYF-aXm5X9Q/viewform?entry.1487425802=CSJ-TWHK-2022-JTKMKC)

---

## 第二步接下來依照下方影片操作取得一個月Qwiklabs訂閱

[![Google cloud study obtain monthly subscription](https://res.cloudinary.com/marcomontalbano/image/upload/v1662042138/video_to_markdown/images/youtube--MVZ6imsfPLo-c05b58ac6eb4c4700831b2b3070cd403.jpg)](https://youtu.be/eKYxUjNgt8c "Google cloud study obtain monthly subscription")

---

成功取得Qwiklabs訂閱後由於上課時間為9/12~9/14會錯過獲得google獎品的日期，因此有心想拿獎品的同學可以先自行完成官方所規定之badges

[活動連結](https://events.withgoogle.com/taiwan-hong-kong-cloud-study-jam/)

實際上課時會帶著你們完成Automate Data Capture at Scale with Document AI這個LAB

歡迎在挑戰LAB時遇到問題的同學提問

有任何問題歡迎直接開[issues](https://github.com/NPUST-DNLAB/Google-cloud-study-obtain-monthly-subscription/issues/new)或是透過向我發送含有問題的Email

[<img src="https://raw.githubusercontent.com/NPUST-DNLAB/Google-cloud-study-obtain-monthly-subscription/d18463ed97d4e3bea6e1b89487160d27cc12abde/email.svg" width="32" height="32">](mailto:q0975040879@gmail.com)
[<img src="https://github.com/NPUST-DNLAB/Google-cloud-study-obtain-monthly-subscription/blob/main/click.gif?raw=true"  width="32" height="32">](mailto:q0975040879@gmail.com)

[<img src="https://raw.githubusercontent.com/NPUST-DNLAB/Google-cloud-study-obtain-monthly-subscription/71c3b33d260f981d7d87b809490712ad29113f1b/line-svgrepo-com.svg"  width="32" height="32">](https://line.me/ti/p/yea9T2X2QZ) 
[<img src="https://github.com/NPUST-DNLAB/Google-cloud-study-obtain-monthly-subscription/blob/main/click.gif?raw=true"  width="32" height="32">](https://line.me/ti/p/yea9T2X2QZ)

---

## 更新來自活動主辦方獲取Qwiklabs monthly-subscription注意事項

```
ericsk — 2022/08/15：

這裡跟大家分享一下過去 Cloud Study Jam 常常有的問題，我這裡盡可能幫大家排除盲點看看會不會更容易成功。
1. 在拿 monthly subscription 的過程中，務必用無痕視窗模式來操作完成。雖然事實上無痕視窗只是建議使用，但每次不用強烈一點的詞很多人就覺得自己一定天生神力不信邪.....

2. 活動給每個人有五個能啟用 monthly subscription 的入口，請選定其中一個就可以完成。這裡會有兩個問題：a) 如果你過去完成過其中一個 Quest，你再選同一個 Quest 也拿不到 monthly subscription，請選其它沒做過的 Quest 作為入口； b) 你不用五個入口都點一次，因為每當你點一個入口（搭配活動碼），系統就會以為你要用該 Quest 作為入口，如果你五個都點了，假設是 甲、乙、丙、丁、戊，那系統會以為你要用「戊」當入口（最新的入口），結果你跑去做甲乙丙丁那當然怎樣都不會有效果喔。結論：選定一個你沒做過的 quest 就好。

3. 如果你確定你不是 2，那在重新測試時，先到選定的 quest 裡 Unroll the quest，然後重新登入（或重開無痕）再依流程做一次，做 lab 前一定要先 Enroll the quest，然後再在該 Quest 下選一個 lab 來做，不能太快就完成，至少要做 5 分鐘以上。

4. 如果你做了一個 lab，不論有沒有做完，只要超過設定的時間，基本上都會完成取得 monthly subscription 的條件。如果你沒有立即看到，不要緊張，稍等一下，或是重新登入再看看，有時候只是剛好遇到了同步的時間差。

5. 真的沒辦法的時候，請聯繫 support@qwiklabs.com 請技術服務團隊來協助您排除困難。
```

---

## 更新來自活動主辦方延長活動提交獎品表單時間

```
Hi everyone,
We have very great news for you. We will extend the deadline to submit the completion form until Sept 18, 2022. 
If you haven't started learning yet, please start your learning journey as soon as possible!

Thank you and We're looking forward to your submission!
```

## Code

> 1
```
export PROJECT_ID=$(gcloud config get-value core/project)
export BUCKET_LOCATION=us-central1
```

> 2
```
gsutil mb -c standard -l ${BUCKET_LOCATION} -b on \
 gs://${PROJECT_ID}-input-invoices
gsutil mb -c standard -l ${BUCKET_LOCATION} -b on \
 gs://${PROJECT_ID}-output-invoices
gsutil mb -c standard -l ${BUCKET_LOCATION} -b on \
 gs://${PROJECT_ID}-archived-invoices

```

> 3
```
bq --location=US mk  -d \
 --description "Form Parser Results" \
 ${PROJECT_ID}:invoice_parser_results
```

> 4
```
cd ~/document-ai-challenge/scripts/table-schema
```

> 5
```
bq mk --table \
invoice_parser_results.doc_ai_extracted_entities \
doc_ai_extracted_entities.json
```

> 6
```
cd ~/document-ai-challenge/scripts
```


> 最後Document AI ID 配對回 Cloud Functions 

[![Automate Data Capture at Scale with Document AI: Challenge Lab Document AI ID to Cloud Functions](https://res.cloudinary.com/marcomontalbano/image/upload/v1662042138/video_to_markdown/images/youtube--MVZ6imsfPLo-c05b58ac6eb4c4700831b2b3070cd403.jpg)](https://www.youtube.com/watch?v=MVZ6imsfPLo "Automate Data Capture at Scale with Document AI: Challenge Lab Document AI ID to Cloud Functions")

> 7
```
export PROJECT_ID=$(gcloud config get-value core/project)   
export CLOUD_FUNCTION_LOCATION=us-central1
gcloud functions deploy process-invoices \
--region=${CLOUD_FUNCTION_LOCATION} \
--entry-point=process_invoice \
--runtime=python37 \
--service-account=${PROJECT_ID}@appspot.gserviceaccount.com \
--source=cloud-functions/process-invoices \
--timeout=400 \
--env-vars-file=cloud-functions/process-invoices/.env.yaml \
--trigger-resource=gs://${PROJECT_ID}-input-invoices \
--trigger-event=google.storage.object.finalize
```

> 8
```
export PROJECT_ID=$(gcloud config get-value core/project)
gsutil cp ~/document-ai-challenge/invoices/* gs://${PROJECT_ID}-input-invoices/
```

##