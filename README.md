# FlappyButterfly-Web

Public WebGL distribution repository for **FlappyButterfly**.

Live site: https://ljq61.github.io/FlappyButterfly-Web/

## Deployment contract

Keep the generated WebGL build at the repository root:

```text
index.html
Build/
TemplateData/
.nojekyll
```

The private/source Unity/Tuanjie project stays in the separate `FlappyButterfly` repository. This repository is only for browser-playable build artifacts.

## First WebGL build

For the first GitHub Pages deployment, use the simplest WebGL output:

- Portrait / 1080×1920 design baseline
- Compression Format: **Disabled**
- Build into an empty local folder
- Upload the **contents** of the WebGL output folder to this repository root
- Keep `.nojekyll`

After upload, `index.html` should reference files under relative paths such as `Build/...`, not absolute `/Build/...` paths.

## Recommended local publish workflow

For small builds you can use GitHub's web upload. For larger Unity/Tuanjie `.data` or `.wasm` files, use Git locally because browser upload limits are lower.

```bash
git clone https://github.com/ljq61/FlappyButterfly-Web.git
cd FlappyButterfly-Web

# Copy the CONTENTS of your WebGL build here, replacing index.html/Build/TemplateData as needed.
# Do not delete .nojekyll.

git add -A
git commit -m "Deploy latest WebGL build"
git push origin main
```

GitHub Pages then serves the new build from:

https://ljq61.github.io/FlappyButterfly-Web/
