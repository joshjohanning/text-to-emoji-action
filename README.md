# text-to-emoji-action

A simple GitHub Composite Action that takes an input (like food, color, animal) and returns back an emoji.

## Usage

```yml
    - name: get emoji
      id: get-emoji
      uses: joshjohanning/text-to-emoji-action@v1
      with:
        color: ${{ inputs.color }}
        food: ${{ inputs.food }}
        animal: ${{ inputs.animal }}
    - name: write emoji
      run: |
        echo "color emoji: ${{ steps.get-emoji.outputs.color-emoji }}"
        echo "food emoji: ${{ steps.get-emoji.outputs.food-emoji }}"
        echo "animal emoji: ${{ steps.get-emoji.outputs.animal-emoji }}"
```

## Inputs

Currently supports:

 - `animal`
 - `color` *(rainbow colors only)*
 - `food` 

*Each input is optional*

## Outputs

- `animal-emoji`
- `food-emoji`
- `color-emoji`

Each can be referenced by setting an `id` to the action reference and then using the output name, like: 

```
${{ steps.<step-id>.outputs.<output> }}
```

*See the example in the [usage](#usage) section above for the full sample*
