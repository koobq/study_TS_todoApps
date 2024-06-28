
# App.css ファイルの詳細解説

## コード

```css
#root {
  max-width: 1280px;
  margin: 0 auto;
  padding: 2rem;
  text-align: center;
}

.logo {
  height: 6em;
  padding: 1.5em;
  will-change: filter;
  transition: filter 300ms;
}
.logo:hover {
  filter: drop-shadow(0 0 2em #646cffaa);
}
.logo.react:hover {
  filter: drop-shadow(0 0 2em #61dafbaa);
}

@keyframes logo-spin {
  from {
    transform: rotate(0deg);
  }
  to {
    transform: rotate(360deg);
  }
}

@media (prefers-reduced-motion: no-preference) {
  a:nth-of-type(2) .logo {
    animation: logo-spin infinite 20s linear;
  }
}

.card {
  padding: 2em;
}

.read-the-docs {
  color: #888;
}
```

## 詳細解説

1. **#root セレクタ**:
    - 最大幅を1280pxに設定し、中央寄せにするために左右のマージンを自動に設定。
    - 上下のパディングを2remに設定し、テキストを中央揃えにします。

2. **.logo クラス**:
    - 高さを6emに設定し、パディングを1.5emに設定。
    - will-changeプロパティを使用して、将来的な変化に備えてパフォーマンスを向上。
    - フィルタの変化に300msのトランジションを設定。
    - ホバー時にdrop-shadowフィルタを適用。

3. **.logo.react クラス**:
    - ホバー時に異なるdrop-shadowフィルタを適用。

4. **@keyframes logo-spin**:
    - 0度から360度まで回転するアニメーションを定義。

5. **@media (prefers-reduced-motion: no-preference)**:
    - 動きを減らす設定が無効な場合、特定のaタグ内の.logo要素に無限に回転するアニメーションを適用。

6. **.card クラス**:
    - 上下左右に2emのパディングを設定。

7. **.read-the-docs クラス**:
    - テキストの色を#888に設定。
