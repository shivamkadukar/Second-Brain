@echo off

REM Get the current branch
for /f %%i in ('git rev-parse --abbrev-ref HEAD') do set current_branch=%%i

REM Check if the current branch is 'master'
if "%current_branch%"=="master" (
    REM Get the latest Git tag
    for /f %%i in ('git describe --tags') do set latest_tag=%%i

    REM Update DynamoDB table
    REM Assuming you have AWS CLI configured
    aws dynamodb update-item --table-name YourTableName --key "{\"Key\": {\"S\": \"YourKey\"}}" --update-expression "SET version = :val" --expression-attribute-values "{\"\":val\": {\"S\": \"%latest_tag%\"}}"
) else (
    echo Not on the master branch. Skipping database update.
)
