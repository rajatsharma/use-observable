# Use Observable

> Single hook for state, effect and everything else

_⚠️ Warning: Highly Experimental 🧪_

## Installation

```sh
yarn add https://github.com/rajatsharma/use-observable
```

## Usage

```tsx
import React from "react";
import { Subject } from "rxjs";
import { map } from "rxjs/operators";
import useObservable from "use-observable";

const App$ = new Subject<string>();

function App() {
  const value = useObservable(
    () => App$.pipe(map((value) => value.toUpperCase())),
    ""
  );

  const onChange = (e: React.FormEvent<HTMLInputElement>) =>
    App$.next(e.currentTarget.value);

  return <input autoFocus onChange={onChange} value={value} />;
}
```
