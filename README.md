# Copilot Instructins
カスタム指示ファイル（*.instructions.md）を集積するためのリポジトリです。サブモジュールとしてプロジェクトリポジトリへ埋め込むことを想定して構成しています。

## Initialize

```bash
cd your-project
git submodule add https://github.com/i7s7-ymp/copilot-instructions.git .github/instructions

cd your-project/.github/instructions
git fetch --tags
git tag
git checkout tags/<tag_name>
```

## Architecture

```mermaid
graph TD
    subgraph "Project A"
        A[Project A]
    end
    subgraph "Project B"
        B[Project B]
    end
    subgraph "Project C"
        C[Project C]
    end

    subgraph "This Repository"
        Common[copilot-instructions]
    end

    A -- "submodule" --> Common
    B -- "submodule" --> Common
    C -- "submodule" --> Common
```