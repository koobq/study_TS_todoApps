
# Todo Application コンポーネント関係図

## コンポーネントの説明

### TodoSummary.tsx
- **Props**: `deleteAllCompleted: () => void`
- **説明**: 
  - 完了したTodoを全て削除するボタンを提供します。
  - 親コンポーネントから `deleteAllCompleted` 関数を受け取り、ボタンのクリックイベントでその関数を呼び出します。

### AddTodoForm.tsx
- **Props**: `addTodo: (title: string) => void`
- **説明**: 
  - 新しいTodoを追加するフォームを提供します。
  - ユーザーがフォームに入力した値を管理するために、内部で `useState` を使用します。
  - フォームが送信されたとき、親コンポーネントから渡された `addTodo` 関数を呼び出して新しいTodoを追加し、入力フィールドをクリアします。

### TodoList.tsx
- **Props**: `todoList: Todo[]`, `changeCompleted: (id: number) => void`, `deleteTodo: (id: number) => void`
- **説明**: 
  - Todoリストを表示します。
  - 各Todoの完了状態を変更するためのチェックボックスと、Todoを削除するためのボタンを提供します。
  - `todoList` はTodo項目の配列で、`changeCompleted` と `deleteTodo` はそれぞれTodoの完了状態を変更する関数と、Todoを削除する関数です。

## ファイル間の関係性

1. **AddTodoForm.tsx**
   - 親コンポーネントから `addTodo` 関数を受け取り、フォームの送信時にその関数を呼び出して新しいTodoを追加します。
   - このコンポーネントは新しいTodoのタイトルを入力するためのUIを提供します。

2. **TodoList.tsx**
   - 親コンポーネントから `todoList` (Todo項目のリスト), `changeCompleted` (Todoの完了状態を変更する関数), `deleteTodo` (Todoを削除する関数) を受け取ります。
   - `todoList` の各Todo項目をマッピングして表示し、各Todo項目には完了状態を変更するためのチェックボックスと削除ボタンを提供します。

3. **TodoSummary.tsx**
   - 親コンポーネントから `deleteAllCompleted` 関数を受け取り、完了したTodoを全て削除するボタンを提供します。
   - ボタンがクリックされたときに `deleteAllCompleted` 関数を呼び出して、完了したTodoを一括削除します。

## 全体の流れ
- **親コンポーネント** は `AddTodoForm`, `TodoList`, `TodoSummary` の3つのコンポーネントをレンダリングし、必要なデータや関数をそれぞれのコンポーネントに渡します。
- **AddTodoForm** は新しいTodoを追加し、その結果を親コンポーネントに通知します。
- **TodoList** は親コンポーネントから受け取ったTodoリストを表示し、各Todoの完了状態の変更や削除を行います。
- **TodoSummary** は完了したTodoを一括削除するボタンを提供し、その操作を親コンポーネントに通知します。

このように、各コンポーネントはそれぞれの役割に応じて親コンポーネントと連携し、Todoアプリケーション全体の機能を実現しています。
