# WhiteSwap API

The WhiteSwap API is a set of **authenticated** endpoints used by market aggregators (e.g. coinmarketcap.com) to surface 
WhiteSwap liquidity and volume information. All information is fetched from the underlying subgraphs.

The API is designed around the CoinMarketCap
[requirements document](https://docs.google.com/document/d/1S4urpzUnO2t7DmS_1dc4EL4tgnnbTObPYXvDeBnukCg).

Prefer the WhiteSwap subgraph for any WhiteSwap queries whenever possible. The respective subgraphs will always have more
recent data.

V1 Subgraph: https://github.com/WhiteSwap/whiteswap-subgraph

## Getting an API Key

We do not porvide an API key for custom users by now.

## Using an API Key

You can use an API key by setting it in the `x-api-key` header, like so:

```sh
curl -v --compressed https://api.ws.exchange/v2/tickers -H 'x-api-key: abcd1234'
```

## Segregated data

Note the data returned by the V1 and V2 endpoints is segregated, i.e. there are no endpoints for combined data from 
both WhiteSwap V1 and V2.

## V1 Documentation

The documentation of the `/v1/` endpoints is [here](./v1.md).

## Deploying the API

The API uses the [serverless framework](https://serverless.com) and can easily be deployed to any AWS account,
via the `yarn sls deploy` command.

In order to configure your AWS account as a target, 
see [the serverless docs](https://www.serverless.com/framework/docs/providers/aws/guide/credentials/).
