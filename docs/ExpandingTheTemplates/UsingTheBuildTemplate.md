# Using the Build Template

First, duplicate the `UMG_MultiMenuTemplate` blueprint and move it into a folder of your choice.

![](https://gyazo.com/ae12c87b0a48f669106dba4f451aa42c.png)

Then open your new Blueprint and locate the following function `GetItemData`, and replace the
`GetDataTableRow` `OutRow` to break out your structure type. Then, connect your items data into
a `Make PTItemDefinition` struct.

![](https://gyazo.com/d3a784b059d1b038ab5a9a80c1be1c4a.png)

In this case, I'm using a custom structure called `StructureBuildData` which contains a lot of
data for building items, but we just need to output the `Icon` and `DisplayName` for the menu.
