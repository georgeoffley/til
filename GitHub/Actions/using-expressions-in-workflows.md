# Using Expressions in GitHub Workflows

[Source](https://docs.github.com/en/actions/learn-github-actions/expressions)

To use expressions in GitHub you need to nest them in `${{ <expression> }}` tags otherwise they'll be treated as strings.