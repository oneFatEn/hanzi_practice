# 课程数据格式说明

## JSON 文件结构

每个年级的课程数据存储在独立的 JSON 文件中，文件名格式：`{年级}.json`

### JSON 格式示例

```json
{
  "gradeName": "一年级上册",
  "units": [
    {
      "unitName": "第一单元",
      "unitDescription": "基础汉字",
      "lessons": [
        {
          "lessonName": "第1课",
          "lessonTitle": "数字汉字",
          "characters": ["一", "二", "三"],
          "description": "学习基础数字汉字的书写"
        }
      ]
    }
  ]
}
```

### 字段说明

- `gradeName`: 年级名称，用于在侧边栏显示一级目录
- `units`: 单元数组
  - `unitName`: 单元名称，用于在侧边栏显示二级目录
  - `unitDescription`: 单元描述（可选）
  - `lessons`: 课时数组
    - `lessonName`: 课时名称，如"第1课"
    - `lessonTitle`: 课时标题（可选），如"数字汉字"
    - `characters`: 该课时需要学习的汉字数组
    - `description`: 课时描述（可选）

### 使用方式

1. 将 JSON 文件放在 `direction` 目录下
2. 文件名会作为一级目录标题显示在侧边栏
3. `units` 中的单元会作为二级目录
4. `lessons` 中的课时会作为可点击的课时选项
5. 点击课时后会在米字格上方显示该课时的 `characters` 数组中的所有字符

### 添加新课程

1. 在 `direction` 目录下创建新的 JSON 文件
2. 按照上述格式填写课程数据
3. 在 `index.html` 的 `jsonFiles` 数组中添加新文件名
4. 重新加载页面即可看到新课程