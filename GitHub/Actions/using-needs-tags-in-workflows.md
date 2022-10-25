# Using Needs Tags In Workflows

Using the `needs` tag in a GitHub workflow tells a job that the stated job needs to have been completed for the current job to run.

### Example

```yml
jobs:
  job1:
  job2:
    needs: job1
  job3:
    needs: [job1, job2]
```

The above example is a set of jobs that depend on the previous job to be complete to be able to run.

#GitHub 