# seoer

[English](./README.md) | 中文

`seoer` 是一个面向 SEO 内容站的 Agent Skill 集合，适合 Codex、Claude Code 或其他能读写文件的编程 Agent 使用。

它把四条高频工作流封装成可复用技能：

- 写作并发布 SEO blog
- 用 SRT 和素材图生成游戏 guide
- 生成高质量 blog 封面图
- 提交、部署、验证上线和可索引状态

仓库结构参考 `baoyu-skills`：每个 skill 都放在 `skills/<skill-name>/SKILL.md`，可以整包安装，也可以单独复制某个 skill 到项目中使用。

## 安装

安装整个集合：

```bash
npx skills add achelie/seoer
```

如果只想在某个项目里使用部分技能，可以把完整 skill 目录复制到项目级 skills 目录：

```text
<project>/.agents/skills/seo-blog-publisher/SKILL.md
<project>/.agents/skills/site-release-indexability-ops/SKILL.md
<project>/.agents/skills/blog-cover/SKILL.md
```

建议按需安装。一次性加载不需要的 skill 会增加每次 Agent 运行的上下文成本。

## 技能列表

### site-release-indexability-ops

![发布与索引验证流程](./screenshots/site-release-indexability-ops.png)

当网站改动准备上线，并且 SEO 可见性很重要时使用它。

适合：

- 提交并推送网站改动
- 部署到 Vercel 或 Cloudflare
- 将分支改动合入 `main` 或 `master`
- 检查生产页面、sitemap、robots、canonical、noindex、favicon、`ads.txt` 和 GSC 相关修复
- 避免从脏工作区部署，把本地临时文件一起上传

示例：

```text
Use $site-release-indexability-ops to commit these blog fixes, deploy production, and verify the changed URLs are indexable.
```

### seo-blog-publisher

![SEO blog 发布流程](./screenshots/seo-blog-publisher.png)

用于长尾词 blog、SaaS/AI 工具 alternatives、价格解释、对比文章和迁移类文章。

适合：

- 查官方来源
- 获取官网截图，保证文章配图不重复
- 写 Reddit 常见抱怨和用户研究部分
- 写适合谁、不适合谁、迁移成本、免费额度、价格限制
- 添加 Article/FAQ/Breadcrumb JSON-LD
- 更新 sitemap、相关文章和 blog 列表
- 配合 `$site-release-indexability-ops` 完成部署

示例：

```text
Use $seo-blog-publisher to write a 3000-word article for "open source ElevenLabs alternatives" with official screenshots, unique images, Reddit complaints, migration cost, and production deployment.
```

### srt-to-game-guide-publisher

![SRT 转游戏攻略流程](./screenshots/srt-to-game-guide-publisher.png)

当一篇攻略的素材来自字幕、视频截图、封面图或本地素材文件夹时使用它。

适合：

- 清理自动生成的 SRT 字幕
- 提取战术、配队、tier、角色名、数字和常见错误
- 确保用户提供的图片都被使用
- 把视频内容改写成原创长文攻略，而不是字幕转录
- 添加 guide metadata、发布时间、相关文章、FAQ/Article JSON-LD 和 sitemap
- 发布完成后的上线验证

示例：

```text
Use $srt-to-game-guide-publisher on this folder. The SRT is the main source, all images must be used, the guide should be SEO-friendly, and it should be deployed after publishing.
```

### blog-cover

![粉彩编辑风 blog 封面流程](./screenshots/blog-cover.png)

用于生成 Gumloop 风格的粉彩 SaaS 封面图，也适合 SEO 文章的 Open Graph 图。

适合：

- AI 工具和 SaaS alternatives 封面
- 价格、额度、订阅限制类封面
- 开发者工作流封面
- SEO 工具、客服工具、项目管理工具对比封面
- 避免同一个站点的封面构图重复
- 生成 1200x630 的可落地项目资产

示例：

```text
Use $blog-cover to generate a 1200x630 pastel SaaS cover for this article. Make it different from the last cover and avoid real product UI.
```

## 推荐组合

- 从选题到上线的 blog：`$seo-blog-publisher` + `$blog-cover` + `$site-release-indexability-ops`
- 从 SRT 到上线的游戏攻略：`$srt-to-game-guide-publisher` + `$site-release-indexability-ops`
- 发布、部署、GSC 或索引问题：`$site-release-indexability-ops`
- 只刷新文章封面：`$blog-cover`

## 仓库结构

```text
seoer/
  README.md
  README.zh.md
  LICENSE
  screenshots/
  skills/
    blog-cover/
      SKILL.md
      agents/openai.yaml
    seo-blog-publisher/
      SKILL.md
      agents/openai.yaml
    site-release-indexability-ops/
      SKILL.md
      agents/openai.yaml
    srt-to-game-guide-publisher/
      SKILL.md
      agents/openai.yaml
```

## 说明

- 公开 skill 名不带斜杠，分别是 `site-release-indexability-ops`、`seo-blog-publisher`、`srt-to-game-guide-publisher` 和 `blog-cover`。
- README 中会用 `achelie/<skill-name>` 作为 GitHub 场景下的展示名称。
- 这些 skill 是工作流指南，不替代实时验证。价格、许可证、搜索结果、GSC 状态和部署状态都应该在执行时重新确认。

## License

MIT
