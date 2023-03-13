# grid-figma-plugin

plugin receives messages through websocket end evaluates them XSS style. Plugin also handles ping messages sent out by the grid editor. Default websocket url is ws://localhost:1337

add teh following test code into a code-block on a potmeter change event:

```
websocket_send('{"plugin": "figma", "action": "for (const node of figma.currentPage.selection) {if (`opacity` in node) {   node.opacity = ',self:potmeter_value()/127,';  }  }"}')

```