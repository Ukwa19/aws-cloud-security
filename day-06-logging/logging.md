# Day 6 – Logging

**Objective:** Enable AWS CloudTrail to log management events and monitor changes in your account.

## CloudTrail Setup
- Trail Name: `day6-management-trail`
- Apply trail to all regions: ✅
- Management events: Read + Write ✅
- Data events / Insights / Network activity: ❌
- S3 bucket: `aws-cloudtrail-logs-892636194429-e3486ec7`
- Log file validation: ✅
- SNS notifications: ✅

## CloudWatch Logs
- Log group: `/aws/cloudtrail/day6-management`
- IAM role: `CloudTrail-CloudWatch-Role`
- Retention: 7 days

## CloudWatch Alarm
- Metric: CloudTrail Management Events → WriteEvents
- Threshold: > 0
- SNS Notification: `day6-iam-write-alert`
- Alarm name: `day6-cloudtrail-write-alarm`

## Notes
- Only management events are logged (cost-effective for labs)  
- Alarm triggers when changes are made to IAM, EC2, VPC, or other AWS resources  
