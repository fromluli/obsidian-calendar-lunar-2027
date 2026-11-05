# Calendar Lunar - 2027 年假期数据

Obsidian Calendar Lunar 插件的 2027 年假期数据更新版本。

## 文件

- `main.js` - 插件主文件（已包含 2027 年数据）
- `manifest.json` - 插件信息
- `holidays-2027.json` - 2027 年假期数据（独立 JSON，供其他用途）

## 安装

复制 `main.js` 和 `manifest.json` 到你的 Obsidian 插件目录：
```
<你的库>/.obsidian/plugins/calendar-lunar/
```
重启 Obsidian。

## 修改假期数据

假期数据在 `main.js` 的 **13200-13258 行**，可以直接编辑：

```javascript
const holidays2027 = [
    { date: '2027-01-01', type: 'rest', name: '元旦' },
    { date: '2027-02-04', type: 'work', name: '春节调休' },  // type: 'work' 表示调休工作日
    // ...
];
```

### 添加新年份（如 2028）

1. 在 `holidays2027` 数组后添加新数组：
```javascript
const holidays2028 = [
    { date: '2028-01-01', type: 'rest', name: '元旦' },
    // 你的数据...
];
```

2. 注册到 Map（约 13254 行）：
```javascript
const allHolidays = new Map([
    [2025, holidays2025],
    [2026, holidays2026],
    [2027, holidays2027],
    [2028, holidays2028],  // 👈 添加这行
]);
```

## 2027 年假期

| 节日 | 日期 | 天数 | 调休 |
|------|------|------|------|
| 元旦 | 1/1-3 | 3天 | - |
| 春节 | 2/5-13 | 9天 | 2/4、2/14 |
| 清明 | 4/3-5 | 3天 | - |
| 劳动节 | 5/1-5 | 5天 | 4/26、5/8 |
| 端午 | 6/9 | 1天 | - |
| 中秋 | 9/15 | 1天 | - |
| 国庆 | 10/1-7 | 7天 | 9/26、10/9 |

数据来源：国务院办公厅 2026-11-05 通知

## 许可

MIT License - 原作者 nairo | 2027 数据更新 Naraku's-DG
