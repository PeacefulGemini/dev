1. 组件中properties的data可使用observer来观察变化
2. 文本换行问题：如果是一串较长连续字母则换行+省略号不会生效，正常使用单词有效。猜测：一串连续字母被识别成一个单词，而换行或省略是按一个单词进行，所以太长的单词无法执行这两种方法。

# Grid布局
## 项目属性
1. 项目位置
    grid-column-start ，grid-column-end ，grid-row-start ， grid-row-end。
    指定项目的四个边框，位于哪根网格线。

2. 简写
    grid-column: <start-line> / <end-line>;
    grid-row: <start-line> / <end-line>;

3. grid-auto-flow 属性
    放置顺序，先行后列 or 先列后行


