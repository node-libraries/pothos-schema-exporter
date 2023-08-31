# pothos-schema-exporter

Plugin to output 'schema.graphql' from pothos to file

## usage

Set the output path to `output`

```ts
import PothosSchemaExporter from "pothos-schema-exporter";

export const builder = new SchemaBuilder({
  plugins: [PothosSchemaExporter],
  pothosSchemaExporter: {
    output: "schema.graphql",
  },
});
```

If `undefined`,`null`,`false` is set, no file will be output

```ts
import PothosSchemaExporter from "pothos-schema-exporter";

export const builder = new SchemaBuilder({
  plugins: [PothosSchemaExporter],
  pothosSchemaExporter: {
    output:
      process.env.NODE_ENV === "development" &&
      path.join(process.cwd(), "graphql", "schema.graphql"),
  },
});
```
