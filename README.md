# google-analytics-next

## Installation

```
npm i google-analytics-next
```
or
```
yarn google-analytics-next
```

## Usage

Add the enable call in your _app.js.

If your App is a class:

```js
import React from "react";
import { enableGoogleAnalytics } from '@/components/google-analytics/google-analytics';


class MyApp extends App {

  componentDidMount() {
    enableGoogleAnalytics(process.env.GOOGLE_ANALYTICS_ID);
  }

  
  render() {
    const { Component, pageProps } = this.props;
    return <Component {...pageProps} />;
  }
}

export default MyApp;
```

If you App is a functional component:
```js
import React, { useEffect } from "react";
import App from "next/app";

import { enableGoogleAnalytics } from '@/components/google-analytics/google-analytics';

function MyApp({ Component, pageProps }) {
  useEffect(() => {
    enableGoogleAnalytics(process.env.GOOGLE_ANALYTICS_ID);
  }, []);
  
  return <Component {...pageProps} />;
}

export default MyApp;
```

It will track routes changes by default.