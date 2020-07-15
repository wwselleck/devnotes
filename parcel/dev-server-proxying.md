# Parcel Server Proxying

## Parcel 1

Parcel 1 does not come with any proxying capabilties in the dev server. The best option is to just set one up manually using `http-proxy-middleware` package, or [parcel-proxy-server](https://www.npmjs.com/package/parcel-proxy-server).

Reference: https://stackoverflow.com/questions/53902896/is-there-a-way-to-proxy-requests-in-parcel-as-in-webpack

## Parcel 2

Parcel 2 does come with dev server proxying. To set it up, you just have to include a `.proxyrc` file at the root of your project.

```json
{
  "/api": {
    "target": "http://localhost:3218/",
    "pathRewrite": {
      "^/api": ""
    }
  }
}

```

Reference: https://v2.parceljs.org/features/api-proxy/
