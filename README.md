# Ocean Arena - 海底竞速与答题挑战 (试玩原型版)

### 快速开始
1. 双击直接在任意现代浏览器（Chrome、Edge、Safari、Firefox）中打开 `index.html`。
2. 点击“开始竞速”即可体验！

### 游戏玩法说明
* **基础控制**：
  * 键盘：`W` / `S` 或 `↑` / `↓` 控制上下潜游，`空格键` 冲刺。
  * 鼠标：上下移动鼠标指引角色游动。
  * 移动端/触摸：右下角提供虚拟按钮（上、下、冲刺）。
* **能量机制**：
  * 持续游动消耗能量，冲刺消耗更快。
  * 约每 10 米出现 `+Energy` 发光能量球，靠近自动拾取补满能量。
* **塑料垃圾与答题事件**：
  * 撞到漂浮的塑料袋垃圾会触发答题弹窗。
  * 答对：获得 +25 能量与 +50 积分，附带 1.5 秒无敌冲刺。
  * 答错：扣除 10 能量并轻微减速。
* **150m Boss 首领挑战**：
  * 到达 150 米触发首领报警警报，巨怪入场。
  * 需连续回答 3 道题弱点攻击，成功击破 Boss 后获得 +500 巨额积分并进入下一深度海域！

### 后续素材包接入方法 (Modular Asset Replacement)
打开 `index.html`，在 `<script>` 标签顶部找到 `ASSET_CONFIG` 配置对象：
```javascript
const ASSET_CONFIG = {
  player: { useImage: true, src: "assets/diver.png" },
  energyOrb: { useImage: true, src: "assets/energy_bubble.png" },
  plasticBag: { useImage: true, src: "assets/plastic_bag.png" },
  boss: { useImage: true, src: "assets/boss_kraken.png" },
  background: { useImage: true, src: "assets/underwater_bg.png" }
};
```
将 `useImage` 设置为 `true` 并填入图片路径，即可立即替换程序化矢量占位符。
同样，在 `QUESTION_BANK` 数组中可以随时增删改各学科的课堂题目。
