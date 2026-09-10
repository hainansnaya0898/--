供应商付款管理系统｜在线多人共享版

1. 创建 Supabase Project。
2. 打开 Supabase → SQL Editor，执行 supabase_schema_and_seed.sql。
3. 在 Supabase Project Settings / Connect 中复制 Project URL 和 Publishable Key。
4. 打开 config.js，填入：url / key。不要填写 secret key。
5. 把整个文件夹上传到 GitHub。
6. 在 Vercel 导入这个 GitHub 仓库并部署。
7. 部署完成后，打开 Vercel 给你的 https://xxxx.vercel.app 地址。

重要：这个 ZIP 默认是“多人共享 MVP”模式，anon 角色拥有供应商表的读写权限，适合内部测试/低风险环境。由于供应商付款数据可能敏感，正式生产环境建议进一步增加 Supabase Auth 登录、角色权限和审计日志，并收紧 RLS。

更新方式：网页每 30 秒自动从 Supabase 刷新一次；修改、新增、删除会直接写入云数据库。

依据：Supabase 官方文档支持通过 CDN 使用 @supabase/supabase-js@2，在浏览器使用 publishable key，并建议通过 RLS 控制表访问。
