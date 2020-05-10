# Coordinating Services in AWS

## Deploy

1. In `serverless.yml`, change the `custom.s3BucketName` to any 
   globally unique name
2. Run `npm i`
3. Run `npm run deploy` which uses `serverless` to deploy a serverless 
   stack using CloudFormation

## Start a Workflow

1. In the AWS Lamba console, create a Test run of the lambda `hbfl-swf-dev-initiator`
1. Then monitor the workflow in the SWF console


## Tear Down

1. Run `npm run delete`


## Notes

- Initial seed data from `s3/incoming` is uploaded to S3 bucket
- How the order of tasks is determined:
  - See `decider.js` `case 'ActivityTaskCompleted'` which calls `activityTaskCompleted.js` 
  which calls a handler in `decider/activityTypes` corresponding to the type of task that
  has been completed. So for example see `deciders/activityTypes/readS3.js` which returns the next
  activity type in the workflow, `ACTIVITY_PROCESS_RESULTS`
