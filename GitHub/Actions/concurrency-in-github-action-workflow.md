# Concurrency in GitHub Action Worflows

[Source](https://docs.github.com/en/actions/using-workflows/workflow-syntax-for-github-actions#concurrency)

You can use the concurrency block to create groups of jobs or worflows and tasks in these groups will only run one at a time. The rest will be queued up.

When a concurrent job or workflow is queued, if another job or workflow using the same concurrency group in the repository is in progress, the queued job or workflow will be pending. Any previously pending job or workflow in the concurrency group will be canceled. To also cancel any currently running job or workflow in the same concurrency group, specify `cancel-in-progress: true`.

You can also specify concurrency at the job level as well using `<job_id>.concurrency` tags.

### Example

```yml
concurrency: 
  group: ${{ github.head_ref || github.run_id }}
  cancel-in-progress: true
```