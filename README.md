# Refresh Environment Variables

## 简介
本仓库用于在 Windows Runner 下调用 `refreshenv` 命令，重新加载指定的环境变量并写入 `GITHUB_ENV`。


## Inputs
| 输入名       | 是否必需 | 描述 |
|--------------|----------|------|
| `env-names`  | 是       | 指定要刷新的环境变量名称，支持逗号分隔或多行格式。




## 使用示例

```yaml
jobs:
  build:
    runs-on: windows-latest
    steps:
      - name: Checkout
        uses: actions/checkout@v3

      - name: RefreshEnv with comma-separated
        uses: OptimalCNC/refreshenv@v1
        with:
          env-names: PATH,MY_CUSTOM_VAR
            
      - name: RefreshEnv with multiline
        uses: OptimalCNC/refreshenv@v1
        with:
          env-names: |
            PATH
            MY_CUSTOM_VAR
```
