# Repro for esModuleInterop bug

## Steps

```
npm install
npm t
```

## Output

```
index.tsx:16:5 - error TS2607: JSX element class does not support attributes because it does not have a 'props' property.

 16     <FlashList
        ~~~~~~~~~~
 17       data={DATA}
    ~~~~~~~~~~~~~~~~~
... 
 19       estimatedItemSize={200}
    ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
 20     />
    ~~~~~~

index.tsx:16:5 - error TS17004: Cannot use JSX unless the '--jsx' flag is provided.

 16     <FlashList
        ~~~~~~~~~~
 17       data={DATA}
    ~~~~~~~~~~~~~~~~~
... 
 19       estimatedItemSize={200}
    ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
 20     />
    ~~~~~~

index.tsx:16:6 - error TS2786: 'FlashList' cannot be used as a JSX component.
  Its instance type 'FlashList<unknown>' is not a valid JSX element.
    Type 'FlashList<unknown>' is missing the following properties from type 'ElementClass': context, setState, forceUpdate, props, and 2 more.

16     <FlashList
        ~~~~~~~~~

index.tsx:18:33 - error TS17004: Cannot use JSX unless the '--jsx' flag is provided.

18       renderItem={({ item }) => <Text>{item.title}</Text>}
                                   ~~~~~~

tsconfig.json:5:12 - error TS5024: Compiler option 'files' requires a value of type Array.

5   "files": "index.tsx"
             ~~~~~~~~~~~


Found 5 errors in 2 files.

Errors  Files
     4  index.tsx:16
     1  tsconfig.json:5
```