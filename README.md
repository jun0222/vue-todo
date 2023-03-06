# 参考記事

- [Vue3 チュートリアル まとめページ](https://qiita.com/TakahiRoyte/items/9033b61a0e528324da4c)

# CRUD

## Create

## Read

```vue
<script>
export default {
  methods: {},
  data() {
    return {
      todos: [
        {
          id: 1,
          isDone: true,
          text: "Vueをマスターする",
        },
        {
          id: 2,
          isDone: false,
          text: "牛乳を買う",
        },
        {
          id: 3,
          isDone: false,
          text: "家賃を払う",
        },
      ],
    };
  },
};
</script>

<template>
  <h1>My ToDo App</h1>
  <input type="text" /><button>追加</button><button>完了済みを削除する</button>
  <ul>
    <li v-for="todo in todos" :key="todo.id">
      <input type="checkbox" /><span>{{ todo.text }}</span>
    </li>
  </ul>
</template>
```

## Update

## Delete

# コマンド

## サーバー起動

`yarn dev`

## サーバー停止

control + c

# エラー解決

### yarn dev で sh: vite: command not found

```sh
yarn add vite
```

vite が入っていないだけ。

### Elements in iteration expect to have 'v-bind:key' directives.eslintvue/require-v-for-key

```vue
<ul>
    <li v-for="todo in todos">
      <input type="checkbox" /><span>{{ todo.text }}</span>
    </li>
  </ul>
```

を

```vue
<ul>
    <li v-for="todo in todos" :key="todo.id">
      <input type="checkbox" /><span>{{ todo.text }}</span>
    </li>
  </ul>
```

にすると解決。react と同様。

[https://github.com/YumaInaura/YumaInaura/issues/3101](https://github.com/YumaInaura/YumaInaura/issues/3101)
