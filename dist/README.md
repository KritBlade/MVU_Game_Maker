# Public Assets

## Default Character Image

Place a PNG file named `default-character.png` in this folder to use as the default character card image when exporting PNG cards.

**Requirements:**
- File name: `default-character.png`
- Format: PNG
- Recommended size: 512x768 or similar portrait dimensions

If no default image is provided and the user doesn't select a custom PNG, they will be prompted to either select an image or add the default.

## Usage

The default image is automatically used when:
1. A character card is loaded
2. User clicks "Download PNG Card"
3. No custom PNG has been selected

The character card JSON data will be embedded into the default image.
