# Sun*CI steps
Contribute to the repository with the following structure:

```JSON
{
    "name": "Step category name",
    "description": "Description about step category",
    "steps": [
         {
            "name": "Step name",
            "description": "Description about step",
            "version": "1.0.0",
            "content": "twig template engine"
        },
        ...
    ]
}
```

Step content example:
```YAML
parameters:
  test_param_1:
    type: string
    default: default_value
    description: The description for test_param_1
  test_param_2:
    type: array
    default: ['default_value_1', 'default_value_2']
    description: The description for test_param_2
image: {{ test_param_1|default('parameters.test_param_1.default') }}
script:
  - echo {{ test_param_2|default(parameters.test_param_2.default) }}
```

Note:
- The content of the step is written by the [twig template engine](https://twig.symfony.com)
- For each language, separate it into a separate file
