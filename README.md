
**Mulai kontrak cerdas di Nibiru.**

# install binary nibiru
```
curl -s https://get.nibiru.fi/! | bash
```

## set config
```
nibid config node https://rpc.itn-1.nibiru.fi:443
nibid config chain-id nibiru-itn-1
nibid config broadcast-mode block
nibid config keyring-backend
```

## install contrac
```
git clone https://github.com/NibiruChain/cw-nibiru
```

## gantikan nama wallet dengan nama key wallet anda jika nama key costum
```
nibid tx wasm store $HOME/cw-nibiru/artifacts-cw-plus/cw20_base.wasm --from wallet --gas-adjustment 1.5 --gas auto --fees 90000unibi  -y

## output
```
code: 0
codespace: ""
data: 0A470A1E2F636F736D7761736D2E7761736D2E76312E4D736753746F7265436F6465122508890B12201525A17A5B98438A26B019FFA184B2A355D225485FCFC87CCBCD524D4A24BE18
events:
- attributes:
  - index: true
    key: c3BlbmRlcg==
    value: bmliaTF4eG42dGdkYzc1Z2RoOWw5dGx2bmN5NDVkeXRzaGt2eGNsMG02YQ==
  - index: true
    key: YW1vdW50
    value: OTAwMDB1bmliaQ==
  type: coin_spent
- attributes:
  - index: true
    key: cmVjZWl2ZXI=
    value: bmliaTE3eHBmdmFrbTJhbWc5NjJ5bHM2Zjg0ejNrZWxsOGM1bDh1OGV6dw==
  - index: true
    key: YW1vdW50
    value: OTAwMDB1bmliaQ==
  type: coin_received
- attributes:
  - index: true
    key: cmVjaXBpZW50
    value: bmliaTE3eHBmdmFrbTJhbWc5NjJ5bHM2Zjg0ejNrZWxsOGM1bDh1OGV6dw==
  - index: true
    key: c2VuZGVy
    value: bmliaTF4eG42dGdkYzc1Z2RoOWw5dGx2bmN5NDVkeXRzaGt2eGNsMG02YQ==
  - index: true
    key: YW1vdW50
    value: OTAwMDB1bmliaQ==
  type: transfer
- attributes:
  - index: true
    key: c2VuZGVy
    value: bmliaTF4eG42dGdkYzc1Z2RoOWw5dGx2bmN5NDVkeXRzaGt2eGNsMG02YQ==
  type: message
- attributes:
  - index: true
    key: ZmVl
    value: OTAwMDB1bmliaQ==
  type: tx
- attributes:
  - index: true
    key: YWNjX3NlcQ==
    value: bmliaTF4eG42dGdkYzc1Z2RoOWw5dGx2bmN5NDVkeXRzaGt2eGNsMG02YS84OTU5
  type: tx
- attributes:
  - index: true
    key: c2lnbmF0dXJl
    value: UElWbzhoc3NUR1hkL0J5akg4NlBSZ2ZwbFVBY2tqdXdwS2x0RXVJMjdORW9FTVUxb0FvaXQ2d2xJMnZtcVFpUEs2b2pUT0ZoR2xvRGJzT3VES21LVnc9PQ==
  type: tx
- attributes:
  - index: true
    key: YWN0aW9u
    value: L2Nvc213YXNtLndhc20udjEuTXNnU3RvcmVDb2Rl
  type: message
- attributes:
  - index: true
    key: bW9kdWxl
    value: d2FzbQ==
  - index: true
    key: c2VuZGVy
    value: bmliaTF4eG42dGdkYzc1Z2RoOWw5dGx2bmN5NDVkeXRzaGt2eGNsMG02YQ==
  type: message
- attributes:
  - index: true
    key: Y29kZV9jaGVja3N1bQ==
    value: MTUyNWExN2E1Yjk4NDM4YTI2YjAxOWZmYTE4NGIyYTM1NWQyMjU0ODVmY2ZjODdjY2JjZDUyNGQ0YTI0YmUxOA==
  - index: true
    key: Y29kZV9pZA==
    value: MTQxNw==
  type: store_code
gas_used: "2140866"
gas_wanted: "3209134"
height: "1727952"
info: ""
logs:
- events:
  - attributes:
    - key: action
      value: /cosmwasm.wasm.v1.MsgStoreCode
    - key: module
      value: wasm
    - key: sender
      value: nibi1xxn6tgdc75gdh9l9tlvncy45dytshkvxcl0m6a
    type: message
  - attributes:
    - key: code_checksum
      value: 1525a17a5b98438a26b019ffa184b2a355d225485fcfc87ccbcd524d4a24be18
    - key: code_id
      value: "1417"
    type: store_code
  log: ""
  msg_index: 0
raw_log: '[{"events":[{"type":"message","attributes":[{"key":"action","value":"/cosmwasm.wasm.v1.MsgStoreCode"},{"key":"module","value":"wasm"},{"key":"sender","value":"nibi1xxn6tgdc75gdh9l9tlvncy45dytshkvxcl0m6a"}]},{"type":"store_code","attributes":[{"key":"code_checksum","value":"1525a17a5b98438a26b019ffa184b2a355d225485fcfc87ccbcd524d4a24be18"},{"key":"code_id","value":"1417"}]}]}]'
timestamp: ""
tx: null
txhash: 4F66C6F701D5870EB07203BD72BBC0612E1517093CC8AD70E8CEB6D8D1E0F95E
```

## save id tx has dan code_id diatas jika anda lupa anda dapat mengecek seperti ini
```
nibid q tx 4F66C6F701D5870EB07203BD72BBC0612E1517093CC8AD70E8CEB6D8D1E0F95E -o json |  jq -r '.raw_log'
```
## memulai contrac nibiru ganti code id dengan milik anda dan nama token dan address 

# contoh
```
INIT='{"name":"jesspoex","symbol":"jpx","decimals":6,"initial_balances":[{"address":"nibi1ervh6j4pd3sr74lu86p5cukucuetsuw6el02hm","amount":"5000000"}],"mint":{"minter":"nibi1ervh6j4pd3sr74lu86p5cukucuetsuw6el02hm"},"marketing":{}}'
nibid tx wasm instantiate 1417 $INIT --from wallet --label "test" --gas-adjustment 1.2 --gas auto --fees 80000unibi --no-admin -y
```

# output jika berhasil
```
code: 0
codespace: ""
data: 0A6D0A282F636F736D7761736D2E7761736D2E76312E4D7367496E7374616E7469617465436F6E747261637412410A3F6E69626931616C726A7361633967756139387A78376D63717667337A3864726B7334336B677270723863396370336371347034387A75663673373963796E65
events:
- attributes:
  - index: true
    key: c3BlbmRlcg==
    value: bmliaTF4eG42dGdkYzc1Z2RoOWw5dGx2bmN5NDVkeXRzaGt2eGNsMG02YQ==
  - index: true
    key: YW1vdW50
    value: ODAwMDB1bmliaQ==
  type: coin_spent
- attributes:
  - index: true
    key: cmVjZWl2ZXI=
    value: bmliaTE3eHBmdmFrbTJhbWc5NjJ5bHM2Zjg0ejNrZWxsOGM1bDh1OGV6dw==
  - index: true
    key: YW1vdW50
    value: ODAwMDB1bmliaQ==
  type: coin_received
- attributes:
  - index: true
    key: cmVjaXBpZW50
    value: bmliaTE3eHBmdmFrbTJhbWc5NjJ5bHM2Zjg0ejNrZWxsOGM1bDh1OGV6dw==
  - index: true
    key: c2VuZGVy
    value: bmliaTF4eG42dGdkYzc1Z2RoOWw5dGx2bmN5NDVkeXRzaGt2eGNsMG02YQ==
  - index: true
    key: YW1vdW50
    value: ODAwMDB1bmliaQ==
  type: transfer
- attributes:
  - index: true
    key: c2VuZGVy
    value: bmliaTF4eG42dGdkYzc1Z2RoOWw5dGx2bmN5NDVkeXRzaGt2eGNsMG02YQ==
  type: message
- attributes:
  - index: true
    key: ZmVl
    value: ODAwMDB1bmliaQ==
  type: tx
- attributes:
  - index: true
    key: YWNjX3NlcQ==
    value: bmliaTF4eG42dGdkYzc1Z2RoOWw5dGx2bmN5NDVkeXRzaGt2eGNsMG02YS84OTYw
  type: tx
- attributes:
  - index: true
    key: c2lnbmF0dXJl
    value: NEFYTU4xeVBmbkF0M0tRSVJ0VExId3lJMDJoa1d2K0FjNmFGNUsyVU15YzR0WW5YT0NqN0lPenZWYUVTV0NlY3U0K0pseVNFVFd2eEJCWlJFNkpVanc9PQ==
  type: tx
- attributes:
  - index: true
    key: YWN0aW9u
    value: L2Nvc213YXNtLndhc20udjEuTXNnSW5zdGFudGlhdGVDb250cmFjdA==
  type: message
- attributes:
  - index: true
    key: bW9kdWxl
    value: d2FzbQ==
  - index: true
    key: c2VuZGVy
    value: bmliaTF4eG42dGdkYzc1Z2RoOWw5dGx2bmN5NDVkeXRzaGt2eGNsMG02YQ==
  type: message
- attributes:
  - index: true
    key: X2NvbnRyYWN0X2FkZHJlc3M=
    value: bmliaTFhbHJqc2FjOWd1YTk4eng3bWNxdmczejhkcmtzNDNrZ3JwcjhjOWNwM2NxNHA0OHp1ZjZzNzljeW5l
  - index: true
    key: Y29kZV9pZA==
    value: MTQxNw==
  type: instantiate
gas_used: "179001"
gas_wanted: "212749"
height: "1727997"
info: ""
logs:
- events:
  - attributes:
    - key: _contract_address
      value: nibi1alrjsac9gua98zx7mcqvg3z8drks43kgrpr8c9cp3cq4p48zuf6s79cyne
    - key: code_id
      value: "1417"
    type: instantiate
  - attributes:
    - key: action
      value: /cosmwasm.wasm.v1.MsgInstantiateContract
    - key: module
      value: wasm
    - key: sender
      value: nibi1xxn6tgdc75gdh9l9tlvncy45dytshkvxcl0m6a
    type: message
  log: ""
  msg_index: 0
raw_log: '[{"events":[{"type":"instantiate","attributes":[{"key":"_contract_address","value":"nibi1alrjsac9gua98zx7mcqvg3z8drks43kgrpr8c9cp3cq4p48zuf6s79cyne"},{"key":"code_id","value":"1417"}]},{"type":"message","attributes":[{"key":"action","value":"/cosmwasm.wasm.v1.MsgInstantiateContract"},{"key":"module","value":"wasm"},{"key":"sender","value":"nibi1xxn6tgdc75gdh9l9tlvncy45dytshkvxcl0m6a"}]}]}]'
timestamp: ""
tx: null
txhash: 4192CA44B54153E7F826BAF5F9CC43E0E53480632D91C84F19B0E0DF5A58EF73
```
## mengatur variable contrac, ganti 1417 dengan code id anda
```
CONTRACT=$(nibid query wasm list-contract-by-code 1417 --output json | jq -r '.contracts[-1]')
```
# mengirim token, ganti address dengan address anda
```
TRANSFER='{"transfer":{"recipient":"nibi1ervh6j4pd3sr74lu86p5cukucuetsuw6el02hm","amount":"100"}}'
```
# jalankan perintah
```
nibid tx wasm execute $CONTRACT $TRANSFER --gas-adjustment 1.5 --gas auto --fees 6000unibi --from wallet -y
```

# output
```
code: 0
codespace: ""
data: 0A260A242F636F736D7761736D2E7761736D2E76312E4D736745786563757465436F6E7472616374
events:
- attributes:
  - index: true
    key: c3BlbmRlcg==
    value: bmliaTF4eG42dGdkYzc1Z2RoOWw5dGx2bmN5NDVkeXRzaGt2eGNsMG02YQ==
  - index: true
    key: YW1vdW50
    value: NjAwMHVuaWJp
  type: coin_spent
- attributes:
  - index: true
    key: cmVjZWl2ZXI=
    value: bmliaTE3eHBmdmFrbTJhbWc5NjJ5bHM2Zjg0ejNrZWxsOGM1bDh1OGV6dw==
  - index: true
    key: YW1vdW50
    value: NjAwMHVuaWJp
  type: coin_received
- attributes:
  - index: true
    key: cmVjaXBpZW50
    value: bmliaTE3eHBmdmFrbTJhbWc5NjJ5bHM2Zjg0ejNrZWxsOGM1bDh1OGV6dw==
  - index: true
    key: c2VuZGVy
    value: bmliaTF4eG42dGdkYzc1Z2RoOWw5dGx2bmN5NDVkeXRzaGt2eGNsMG02YQ==
  - index: true
    key: YW1vdW50
    value: NjAwMHVuaWJp
  type: transfer
- attributes:
  - index: true
    key: c2VuZGVy
    value: bmliaTF4eG42dGdkYzc1Z2RoOWw5dGx2bmN5NDVkeXRzaGt2eGNsMG02YQ==
  type: message
- attributes:
  - index: true
    key: ZmVl
    value: NjAwMHVuaWJp
  type: tx
- attributes:
  - index: true
    key: YWNjX3NlcQ==
    value: bmliaTF4eG42dGdkYzc1Z2RoOWw5dGx2bmN5NDVkeXRzaGt2eGNsMG02YS84OTYx
  type: tx
- attributes:
  - index: true
    key: c2lnbmF0dXJl
    value: OW1VZ1plK3pwaUZTK1Q0QWR1cHBERWI3OFBJYUZxb2N2Z0VKQUdnakNKMXNDY0hTNUw1VEh0eHhVdmc0VjVValpYNU5VL0FTcXFDY1l1TkRQVTB1Qnc9PQ==
  type: tx
- attributes:
  - index: true
    key: YWN0aW9u
    value: L2Nvc213YXNtLndhc20udjEuTXNnRXhlY3V0ZUNvbnRyYWN0
  type: message
- attributes:
  - index: true
    key: bW9kdWxl
    value: d2FzbQ==
  - index: true
    key: c2VuZGVy
    value: bmliaTF4eG42dGdkYzc1Z2RoOWw5dGx2bmN5NDVkeXRzaGt2eGNsMG02YQ==
  type: message
- attributes:
  - index: true
    key: X2NvbnRyYWN0X2FkZHJlc3M=
    value: bmliaTFhbHJqc2FjOWd1YTk4eng3bWNxdmczejhkcmtzNDNrZ3JwcjhjOWNwM2NxNHA0OHp1ZjZzNzljeW5l
  type: execute
- attributes:
  - index: true
    key: X2NvbnRyYWN0X2FkZHJlc3M=
    value: bmliaTFhbHJqc2FjOWd1YTk4eng3bWNxdmczejhkcmtzNDNrZ3JwcjhjOWNwM2NxNHA0OHp1ZjZzNzljeW5l
  - index: true
    key: YWN0aW9u
    value: dHJhbnNmZXI=
  - index: true
    key: ZnJvbQ==
    value: bmliaTF4eG42dGdkYzc1Z2RoOWw5dGx2bmN5NDVkeXRzaGt2eGNsMG02YQ==
  - index: true
    key: dG8=
    value: bmliaTFjcjI2dnd0OG16Z3k1djY2NjU3M2x2NTBycmo1NjM0OHh4Z2E5cw==
  - index: true
    key: YW1vdW50
    value: MTAw
  type: wasm
gas_used: "134005"
gas_wanted: "198906"
height: "1728087"
info: ""
logs:
- events:
  - attributes:
    - key: _contract_address
      value: nibi1alrjsac9gua98zx7mcqvg3z8drks43kgrpr8c9cp3cq4p48zuf6s79cyne
    type: execute
  - attributes:
    - key: action
      value: /cosmwasm.wasm.v1.MsgExecuteContract
    - key: module
      value: wasm
    - key: sender
      value: nibi1xxn6tgdc75gdh9l9tlvncy45dytshkvxcl0m6a
    type: message
  - attributes:
    - key: _contract_address
      value: nibi1alrjsac9gua98zx7mcqvg3z8drks43kgrpr8c9cp3cq4p48zuf6s79cyne
    - key: action
      value: transfer
    - key: from
      value: nibi1xxn6tgdc75gdh9l9tlvncy45dytshkvxcl0m6a
    - key: to
      value: nibi1cr26vwt8mzgy5v666573lv50rrj56348xxga9s
    - key: amount
      value: "100"
    type: wasm
  log: ""
  msg_index: 0
raw_log: '[{"events":[{"type":"execute","attributes":[{"key":"_contract_address","value":"nibi1alrjsac9gua98zx7mcqvg3z8drks43kgrpr8c9cp3cq4p48zuf6s79cyne"}]},{"type":"message","attributes":[{"key":"action","value":"/cosmwasm.wasm.v1.MsgExecuteContract"},{"key":"module","value":"wasm"},{"key":"sender","value":"nibi1xxn6tgdc75gdh9l9tlvncy45dytshkvxcl0m6a"}]},{"type":"wasm","attributes":[{"key":"_contract_address","value":"nibi1alrjsac9gua98zx7mcqvg3z8drks43kgrpr8c9cp3cq4p48zuf6s79cyne"},{"key":"action","value":"transfer"},{"key":"from","value":"nibi1xxn6tgdc75gdh9l9tlvncy45dytshkvxcl0m6a"},{"key":"to","value":"nibi1cr26vwt8mzgy5v666573lv50rrj56348xxga9s"},{"key":"amount","value":"100"}]}]}]'
timestamp: ""
tx: null
txhash: 1B1CBFE7902D4B33CAFD63269F38988050C472ED8051EEE96AA1E95E91E47986
```

## done dan tunggu di exploler untuk hasil, jika melakukan langkah dari pertama akan berhasil
