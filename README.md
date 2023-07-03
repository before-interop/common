# TMF Common

Common components for Interop TMF based projects.

## Tool APIs

Swagger documentation for the tool APIs is available at [https://before-interop.github.io/common/](https://before-interop.github.io/common/).

## Usage

### Include a reference in your documentation

```yaml
responses:
  '400':
    $ref: https://raw.githubusercontent.com/before-interop/common/main/common/responses/errors.openapi.yaml#/components/responses/Error-400
```

### Extend a component

```yaml
components:
  schemas:
    MyObject:
      allOf:
        - $ref: https://raw.githubusercontent.com/before-interop/common/main/common/schemas/Entity.openapi.yaml#/components/schemas/Entity
      properties:
        myProperty:
          type: string
```

## Contributing

Contributions are what make the open source community such an amazing place to learn, inspire, and create.
Any contributions you make are **greatly appreciated**.

If you have a suggestion that would make this better, please fork the repo and create a pull request.

1. Fork the Project
2. Create your Branch (git checkout -b amazingFeature)
3. Commit your Changes (git commit -m 'Add some AmazingFeature')
4. Push to the Branch (git push origin amazingFeature)
5. Open a Pull Request

## License

Distribution of this project is governed by the Apache License, Version 2.0 (see [LICENSE](LICENSE) for more information).

## Projects using this library

It is not mandatory to list your project here,
but it would be nice to see who is using this library.
But the real added value is to notify you **when a breaking change is coming**.

The following projects are using this library:

* [AnomalieAdresse](https://github.com/before-interop/anomalieAdresse)
* [Malfaçon](https://github.com/before-interop/malfacon)
