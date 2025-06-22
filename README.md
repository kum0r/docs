# Mintlify Starter Kit

Click on `Use this template` to copy the Mintlify starter kit. The starter kit contains examples including

- Guide pages
- Navigation
- Customizations
- API Reference pages
- Use of popular components

### Development

Install the [Mintlify CLI](https://www.npmjs.com/package/mintlify) to preview the documentation changes locally. To install, use the following command

```
npm i -g mintlify
```

Run the following command at the root of your documentation (where docs.json is)

```
mintlify dev
```

### Publishing Changes

Install our Github App to auto propagate changes from your repo to your deployment. Changes will be deployed to production automatically after pushing to the default branch. Find the link to install on your dashboard.

#### Troubleshooting

- Mintlify dev isn't running - Run `mintlify install` it'll re-install dependencies.
- Page loads as a 404 - Make sure you are running in a folder with `docs.json`

### Updating openapi json and auto generate mdx files

- Export / download the openapi spec from running FastAPI instance docs
- Copy contents of the openapi.json into api-reference/openapi.json, replacing existing content
- rename api-reference/generated folder to api-reference/old-generated
  Run the following command to regenearate the docs

```bash
npx @mintlify/scraping@latest openapi-file api-reference/openapi.json -o api-reference/generated
```

- Check if all files were generated. Change mdx front matter as needed
- Delete old-generated folder
