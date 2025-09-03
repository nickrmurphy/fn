# fn

A collection of tiny zero dependency utilities that support type safety and functional programming.

## Installation

```bash
bun install
```

## Examples

### Option
```typescript
import { some, none } from './lib/option.ts';

const value = some(42);
const empty = none();

// Pattern matching
if (value.tag === 'some') {
	console.log(value.value); // 42
}
```

### Result
```typescript
import { ok, err } from './lib/result.ts';

const success = ok("Hello");
const failure = err("Something went wrong");

// Pattern matching
if (success.tag === 'ok') {
	console.log(success.data); // "Hello"
}
```

### Chain
```typescript
import { chain } from './lib/chain.ts';

const result = chain(10)
	.pipe(x => x * 2)
	.tap(x => console.log(`Doubled: ${x}`))
	.pipe(x => x + 5)
	.get(); // 25
```

## Development

```bash
bun test                    # Run all tests
bun run check              # Lint and format
bun run index.ts           # Run main entry point
```
