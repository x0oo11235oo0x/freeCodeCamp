# Cypress テストを追加する方法

ページの機能やレイアウトを変更する可能性がある JavaScript、CSS、または HTML を変更する際には、対応する [Cypress](https://docs.cypress.io) 統合テストを追加することが重要です。

Cypress テストもしくは「specs」の書き方については、Cypress の公式 [ドキュメント ](https://docs.cypress.io/guides/getting-started/writing-your-first-test.html) をご覧ください。

## テストを追加する場所

- Cypress テストは `./cypress` ディレクトリにあります。

- カリキュラムモジュールの Cypress テストは、対応するカリキュラムディレクトリ、すなわち `cypress/integration/learn/responsive-web-design/basic-css/index.js` にあります。

## テストを実行する方法

> [!NOTE] GitPod を使用している場合は、[Cypress と GitPod の設定](/how-to-add-cypress-tests#cypress-gitpod-setup) を参照してください。

### 1. MongoDB とクライアントアプリケーションが動作していることを確認する

- [MongoDB を起動し、データベースをシードします。](/how-to-setup-freecodecamp-locally#step-3-start-mongodb-and-seed-the-database)

- [freeCodeCamp クライアントアプリケーションと API サーバーを起動します。](/how-to-setup-freecodecamp-locally#step-4-start-the-freecodecamp-client-application-and-api-server)

### 2. Cypress テストを実行する

`dev` を `prd` に置き換えて本番ビルドに対するテストを実行します。

- `./cypress` ディレクトリで、すべてのテストを実行します。

  ```console
  npm run cypress:dev:run
  ```

- 単一のテストを実行します。

  ```console
  npm run cypress:dev:run -- --spec=cypress/pathToYourSpec/youSpecFileName.js
  ```

- 開発ビルドを作成するには、開発サーバーを起動し、既存の cypress エンドツーエンドテストをすべて実行します。

  ```console
  npm run e2e:dev:run
  ```

## Cypress と GitPod の設定

### 1. Ensure Development Environment is Running

GitPod 環境を起動しても自動的に環境が構築されない場合は、以下を実行します。

- Start the database

```console
mongod
```

- Seed the database

```console
npm run seed
```

- Develop the server and client

```console
npm run develop
```

### 2. Install Cypress Build Tools

```console
npm run cypress:install-build-tools
```

- When prompted in the terminal, select your keyboard layout by language/area

これで、[Cypress を実行することができます ](/how-to-add-cypress-tests#_2-run-the-cypress-tests)。
