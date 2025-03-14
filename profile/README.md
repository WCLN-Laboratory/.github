# Location Awareness in Next-Generation Networks

## Instructions for Generating `answer.txt`
The file `answer.txt` must contain a single line with the format:

```
0.XX
```

Where `0.XX` represents the horizontal localization error achieved at the 90th percentile. The unit of measure must be meters.

## Example
If the competitor achieves a horizontal localization error of <span style="letter-spacing:-1px;">0.86 m</span> at the 90th percentile, then the file should contain:

```
0.86
```

## Notes
- The value should be rounded to two decimals and must be a single line.
- Ensure there are no extra spaces or characters in the output.

## Sample Python Code to Generate `answer.txt`
```python
percentile_90_accuracy = 0.86
with open("answer.txt", "w") as file:
    file.write(f"{percentile_90_accuracy:.2f}\n")
```
This script takes an accuracy percentage and formats it correctly in `answer.txt`. 🎯
