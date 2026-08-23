# **You Have Not Seen My Colors**

category: Cryptography

Author: TitanCode

# **Challenge Description:**

Elian gave you this challenge. Find meaning in the noise, then prove what you decided to the private endpoint.

The answer is lowercase with words joined by underscores.

**No hint**

# **Files**
| File | Description |
|------|-------------|
| crypto_you-have-not-seen-my-colors (1).tar | the attached file was the main clue/ciphertext |
| an instance | where you have to submit the phrase and get the flag |

# **Analysis** 

The description indicates that the phrase will be in lower case.

when opened the file:

it contained:

image.png, a 100 × 100 pixel RGB image that visually looked mostly like random/noisy colors.

used that image.png as the main input for solving the challenge. analyzed its pixel/color information—especially the Red, Green, 

and Blue (RGB) channels and their underlying bits—because the challenge hint “You Have Not Seen My Colors” pointed toward

information being hidden in the image's color data.

After that, The instance had a image to download 

here, I assumed that by decoding the phrase in image and by submitting that phrase there we get the flag automatically.

# Image:

<img width="100" height="100" alt="image" src="https://github.com/user-attachments/assets/101d8b34-71ed-41a8-90ed-24bc83845b8e" />

It was an noisy image

# Solution:

just had to decode the image to get phrase

as it was an noisy so it was not easy, researched some and got to know that:

A normal RGB image stores every pixel as three numbers:

Pixel = (Red, Green, Blue)

Each of those numbers is 8 bits:

R = r7 r6 r5 r4 r3 r2 r1 r0

G = g7 g6 g5 g4 g3 g2 g1 g0

B = b7 b6 b5 b4 b3 b2 b1 b0

Then again researched some and got this finding:

The image looked like random colors because I was looking at the complete RGB values. But instead of treating each pixel as a color,
separated the channels and examined their individual binary bit layers.

<img width="750" height="450" alt="image" src="https://github.com/user-attachments/assets/aebf0eca-7bf4-43d0-a9ca-8326969e4641" />

Think of an image as having hidden layers:

Normal image

→ R / G / B channels

→ each channel split into bit 0, bit 1, ... bit 7

→ inspect/combine those layers

→ a structured visual pattern appears

→ ZDK MASTER OF CTF

→ normalize as master_of_ctf

got the phrase "master_of_ctf" then submitted that phrase in the instance by which we got the flag in front.

# 🚩 **Flag:**

zdk{MA5teR_OF_coLOR5_anD_C7F}
