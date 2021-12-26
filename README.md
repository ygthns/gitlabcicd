# GITLAB CI/CD
This is a reposiroty for record my notes and configs about gitlab ci/cd processes. 


## Notes

- This will execute this job only for master branch
    ```
    only:
      - master 
  
    ```
- This will execute this job only during merge requests
    ```
    only:
      - merge_requests
  
    ```

- With the following two commands, i block deployment of production until i trigger it manually.
    ```
    when: manual
    allow_failure: false
    ```

- You can disable a job with adding a dot(.) just before job's name.
    ```
    .test website:
      stage: test
      script:
        - npm install
    ```
    
 - Don't run this job when pipeline triggered by schedule
    ```
      test website:
        stage: test
        script:
           - npm install
         except:
           - schedules

    ```
   
  - Setting variables
    ```
      variables:
        STAGING_DOMAIN: redturtlebing-staging.surge.sh
        PRODUCTION_DOMAIN: redturtlebing.surge.sh

    ```

## Author Information
Yigithan Saglam - saglamyigithan@gmail.com

## Reference
@Valentin Despa (GitLab CI: Pipelines, CI/CD and DevOps for Beginners) : https://www.udemy.com/course/gitlab-ci-pipelines-ci-cd-and-devops-for-beginners/
