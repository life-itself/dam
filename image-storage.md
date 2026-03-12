# Image storage discussion

### Situation

- Currently store all images and other static assets directly into the main site folder on github (using git-lfs)
- We are storing lots of images for our ecosystem wiki (~100s or even 1000s). We don't want to think about the sizes of images. Images often end up being ~0.5-1MB => total amount could be GB or more.

### Complication

- slows build as have to download 1GB+ of assets
- working with repo is more painful as have
- no image resizing atm
- github won't like having GBs of images. Putting them in LFS is one solution but makes stuff more complex and painful e.g. you can't upload files directly on github interface (any other issues?).

### Question

where should we store images and how does that integrate with resizing such that ...

- ...
- ...

### Hypothesis

No answer yet!

Note pros:

- Assets and files in same place which means adding stuff is super simple (no need for two steps: upload my image, then link it etc)

What are the alternatives?

- Use cloudflare r2 with a custom domain plus image resizing - https://developers.cloudflare.com/r2/buckets/public-buckets/
- Cost?
- How to upload?
  - r2 dashboard or wrangler (needs access to cloudflare)
  - any r2 compatible command line tool with correct keys
  - (someday) custom plugin for obsidian like https://github.com/gavvvr/obsidian-imgur-plugin for imgur

## Notes

#todo dig out old issues about DAM etc

### What we would love

- integrated experience for editors
  - just paste images or other assets and they automatically get uploaded
  - widget for resizing (or good instructions for doing so in raw html etc)
- sustainability and simplicity of tech architecture (both on cost and team time)

### Obsidian plugins

- https://github.com/addozhang/obsidian-image-upload-toolkit
- https://github.com/gavvvr/obsidian-imgur-plugin ⭐175
- https://github.com/renmu123/obsidian-image-auto-upload-plugin ⭐286
