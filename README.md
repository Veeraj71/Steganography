# Steganography

Steganography is the practice of hiding secret messages within other non-secret data, such that the presence of the hidden messages is concealed. This project focuses on implementing steganography techniques to encode and decode messages within digital images.

## Features

- **Encode Message**: Hide a secret text message within an image by modifying the least significant bits of the image's pixels.
- **Decode Message**: Extract the hidden text message from an image that has been encoded using this tool.

## How It Works

The technique used in this project involves manipulating the least significant bit (LSB) of each pixel in the image to hide the message. This method allows for the concealment of data in a way that is imperceptible to the human eye. ([GitHub](https://github.com/RoliSoft/Steganography/blob/master/README.md?utm_source=chatgpt.com))

## Usage

1. **Encoding a Message**:
   - Select the image in which you want to hide the message.
   - Input the secret text message you wish to conceal.
   - The program will process the image and embed the message by altering the LSBs of the pixels.

2. **Decoding a Message**:
   - Provide the image that contains the hidden message.
   - The program will analyze the LSBs of the pixels to reconstruct and reveal the hidden text message.

## Implementation Details

The process begins by normalizing the image data, ensuring that each RGB value is even. This normalization facilitates the encoding process. The secret message is then converted into its binary representation, with each character represented by 8 bits. These bits are embedded into the normalized image, with 3 bits hidden per pixel. Consequently, the maximum length of a message that can be hidden in an image is determined by the formula:

```
Image Width * Image Height * 3
------------------------------
             8
```

After embedding the message, the image is saved in a lossless format to preserve the hidden data. To retrieve the message, the program examines the LSBs of the pixels to reconstruct the binary representation of the original text. ([GitHub](https://github.com/stylesuxx/steganography/blob/gh-pages/README.md?utm_source=chatgpt.com))

## Security Considerations

While steganography hides the existence of a message, it does not encrypt the content. For enhanced security, it's advisable to encrypt the message before embedding it into the image. This way, even if the hidden message is discovered, its content remains protected. ([GitHub](https://github.com/stylesuxx/steganography/blob/gh-pages/README.md?utm_source=chatgpt.com))

## Requirements

- Python 3.x
- Pillow library for image processing

## Installation

1. Clone the repository:

   ```bash
   git clone https://github.com/Veeraj71/Steganography.git
   ```

2. Navigate to the project directory:

   ```bash
   cd Steganography
   ```

3. Install the required dependencies:

   ```bash
   pip install -r requirements.txt
   ```

## Usage

To encode a message into an image:

```bash
python steganography.py encode -i input_image.png -o output_image.png -m "Your secret message"
```

To decode a message from an image:

```bash
python steganography.py decode -i output_image.png
```

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

## Acknowledgments

- [RoliSoft's Steganography Project](https://github.com/RoliSoft/Steganography)
- [stylesuxx's Steganography Online](https://github.com/stylesuxx/steganography)

These projects provided valuable insights into the implementation of steganography techniques. 
