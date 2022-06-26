# sam-app
## 参考
- [aws-serverless-batch-architecture](https://github.com/aws-samples/aws-serverless-batch-architecture)

## requirements
- AWS SAM CLI
- Python3.9

## 概要
### S3NotificationLambda
- 通知を受け取ってCSVBatchMainOrchestratorをキックするラムダ
- 全ての入り口
- (当初の想定のまま名前はS3Notificationになってる)
### CSVBatchMainOrchestrator
- 入力のCSVをchunkに分割しS3に保存
- 分割したchunk毎にCSVBatchProcessChunkをキック
### CSVBatchProcessChunk
- CSVを読み込みprintするだけ
