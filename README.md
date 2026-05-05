# Graylog's Oxfmt Config

This package is a shared [oxfmt](https://oxc.rs/docs/guide/usage/formatter) config for Graylog projects. Its rules mirror [`@graylog/prettier-config`](https://github.com/Graylog2/prettier-config).

Unlike Prettier, oxfmt does not support extending configurations from a package directly. Instead, create an `oxfmt.config.ts` in your project root that imports and re-exports this config — oxfmt picks it up automatically:

```ts
import { defineConfig } from 'oxfmt';
import config from '@graylog/oxfmt-config';

export default defineConfig(config);
```

`defineConfig` from `oxfmt` provides type inference for the config object. You can spread the shared config and override fields locally if needed:

```ts
import { defineConfig } from 'oxfmt';
import config from '@graylog/oxfmt-config';

export default defineConfig({ ...config, printWidth: 100 });
```

See the [oxfmt configuration reference](https://oxc.rs/docs/guide/usage/formatter#configuration) for the full list of supported options.
