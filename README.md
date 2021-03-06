## scratch-vm
#### Scratch VM is a library for representing, running, and maintaining the state of computer programs written using [Scratch Blocks](https://github.com/LLK/scratch-blocks).

[![Build Status](https://travis-ci.org/LLK/scratch-vm.svg?branch=develop)](https://travis-ci.org/LLK/scratch-vm)
[![Dependency Status](https://david-dm.org/LLK/scratch-vm.svg)](https://david-dm.org/LLK/scratch-vm)
[![devDependency Status](https://david-dm.org/LLK/scratch-vm/dev-status.svg)](https://david-dm.org/LLK/scratch-vm#info=devDependencies)

## Installation
```bash
npm install scratch-vm
```

## Setup
```js
var VirtualMachine = require('scratch-vm');
var vm = new VirtualMachine();

// Block events
workspace.addChangeListener(vm.blockListener);
var flyoutWorkspace = workspace.toolbox_.flyout_.workspace_;
flyoutWorkspace.addChangeListener(vm.flyoutBlockListener);

// Run threads
vm.runtime.start();
```

## Standalone Build
```bash
make build
```

```html
<script src="/path/to/vm.js"></script>
<script>
    var vm = new window.VirtualMachine();
    // do things
</script>
```

## Abstract Syntax Tree

#### Overview
The Virtual Machine constructs and maintains the state of an [Abstract Syntax Tree](https://en.wikipedia.org/wiki/Abstract_syntax_tree) (AST) by listening to events emitted by the [scratch-blocks](https://github.com/LLK/scratch-blocks) workspace via the `blockListener`. At any time, the current state of the AST can be viewed by inspecting the `vm.runtime.blocks` object.

#### Anatomy of a Block
```json
{
    "7AJZR#NA;m*b}R]pdq63": {
      "id": "7AJZR#NA;m*b}R]pdq63",
      "opcode": "control_wait",
      "inputs": {
        "DURATION": {
          "name": "DURATION",
          "block": ",xA8/S!Z6+kR,9dph.rO"
        }
      },
      "fields": {},
      "next": null,
      "topLevel": true
    },
    ",xA8/S!Z6+kR,9dph.rO": {
      "id": ",xA8/S!Z6+kR,9dph.rO",
      "opcode": "math_number",
      "inputs": {},
      "fields": {
        "NUM": {
          "name": "NUM",
          "value": "1"
        }
      },
      "next": null,
      "topLevel": false
    }
  }
```

## Testing
```bash
make test
```

```bash
make coverage
```

## Donate
We provide [Scratch](https://scratch.mit.edu) free of charge, and want to keep it that way! Please consider making a [donation](https://secure.donationpay.org/scratchfoundation/) to support our continued engineering, design, community, and resource development efforts. Donations of any size are appreciated. Thank you!
