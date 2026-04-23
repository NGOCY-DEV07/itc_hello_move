# itc_hello

Smart contract Move don gian tren Sui de tao va cap nhat loi chao duoc chia se cong khai.

## Module

- `itc::greeting`

Module nay dinh nghia object `Greeting` (shared object) voi:

- `new(ctx: &mut TxContext)`: tao `Greeting` moi voi text mac dinh `"Hello world!"` va share object.
- `update_text(greeting: &mut Greeting, new_text: string::String)`: cap nhat noi dung text cua `Greeting`.

## Da deploy

Package ID da deploy:

`0x59339cdf0d6218c7ba5b5dd545312d8d9af3fae21d8f1298426926f03fee7289`

## Cau truc thu muc

```text
itc_hello/
  Move.toml
  sources/
    itc_hello.move
```

## Cach build

```bash
sui move build
```

## Cach test

```bash
sui move test
```

## Publish (tham khao)

Neu ban muon deploy package moi:

```bash
sui client publish --gas-budget 100000000
```

## Goi ham sau khi deploy (tham khao)

- Tao Greeting moi:

```bash
sui client call \
  --package <PACKAGE_ID> \
  --module greeting \
  --function new \
  --gas-budget 10000000
```

- Cap nhat text Greeting:

```bash
sui client call \
  --package <PACKAGE_ID> \
  --module greeting \
  --function update_text \
  --args <GREETING_OBJECT_ID> "Xin chao Sui!" \
  --gas-budget 10000000
```
