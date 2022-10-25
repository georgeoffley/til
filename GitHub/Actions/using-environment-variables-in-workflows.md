# Using Environment Variables In Workflows

[Source](https://docs.github.com/en/actions/learn-github-actions/expressions)

Using the `env` block in a workflow file you can set environment variables for use in the different jobs you have set up.

### Example

```yml
env:
  SERVER: production
```

This will give us the varilable `SERVER` with the value `production`.

#GitHub 