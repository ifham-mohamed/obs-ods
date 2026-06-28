
2024-07-28 19:18

Status:

Tags: #UOM #L2S2-S4 #Graphic-Design



# Graphic Systems Computer Color Systems


### Three-Color Theory(trichromatic theory)

> Human eyes only perceive three colors of light: **red**, **blue**, and **green**. The wavelengths of these three colors can be combined to create every color on the visible light spectrum. -**Young-Helmholtz** 

Human visual system has two types of sensors  
- Rods: monochromatic, night vision  
- Cones  
	- Color sensitive  
	- Three types of cone  
	- Only three values (the tristimulus values) are sent to the brain
### Additive and Subtractive Color
#### Additive Color
Form a color by adding amount of three primary colors
- CRTs, projection systems

Primary - <mark style="background: #FF5582A6;">Red</mark>, <mark style="background: #BBFABBA6;">Green</mark>, <mark style="background: #ADCCFFA6;">Blue</mark>

#### Subtractive Color
Form a color by filtering white light with <mark style="background: #ABF7F7A6;">Cyan (C)</mark>, <mark style="background: #D2B3FFA6;">Magenta (M)</mark>, and <mark style="background: #FFF3A3A6;">Yellow (Y)</mark> filters 
- Printing

### Color Models and how they are used in graphics.

### Color Models

- The purpose of a color model is to facilitate the specification of colors in some standard way
- A color model provides a coordinate system and a subspace in it where each color is represented by a single point

#### RGB Model
Uses three primary colors and create a larger range of colors.    
Used in light emitting devices    
- Color CRT monitors    
Additive   
- Individual contributions of each primary color added together    
- C = rR + gG + bB, where r, g, b ∈ [0, 1]

#### RGB Color Cube
[[Lecture3.pdf#page=12&selection=0,0,4,4|Lecture3, page 12]]

> [!NOTE]
> - R + G = (1, 0, 0) + (0, 1, 0) = (1, 1, 0) = Y     
> - R + B = (1, 0, 0) + (0, 0, 1) = (1, 0, 1) = M     
> - B + G = (0, 0, 1) + (0, 1, 0) = (0, 1, 1) = C    
> - R + G + B = (1, 1, 1) = W     
> - 1 – W = (0, 0, 0) = BLK

#### CMYK Model

<mark style="background: #ABF7F7A6;">C</mark><mark style="background: #D2B3FFA6;">M</mark><mark style="background: #FFF3A3A6;">Y</mark>: Complements of <mark style="background: #FF5582A6;">R</mark><mark style="background: #BBFABBA6;">G</mark><mark style="background: #ADCCFFA6;">B</mark>    
Used in light absorbing devices    
- Hardcopy/Printing devices    
Subtractive    
- Color specified by what is subtracted from white light.    
- Cyan absorbs red, magenta absorbs green, and yellow absorbs blue
[[Lecture3.pdf#page=14&selection=0,18,18,1|Lecture3, page 14]]

**Q)**
1. Briefly explain how to convert between RGB and CMYK. 
	1. **RGB to CMYK Conversion**:
	    - **RGB (Red, Green, Blue)** is an additive color model used in digital displays and screens. It combines red, green, and blue light to create a wide range of colors.
	    - **CMYK (Cyan, Magenta, Yellow, Key/Black)** is a subtractive color model used in printing. It represents the four ink plates used in color printing.
	    - To convert RGB to CMYK, follow these steps:
	        - Normalize the RGB values by dividing each component (R, G, B) by 255 to obtain values in the range of 0 to 1.
	        - Calculate the CMYK values using the following formulas:
	            - Cyan © = 1 - Red ®
	            - Magenta (M) = 1 - Green (G)
	            - Yellow (Y) = 1 - Blue (B)
	            - Black (K) = min(C, M, Y)
	    - Note that the CMYK model includes a black component (K) to improve color accuracy in printing.
	
	1. **CMYK to RGB Conversion**:
	    - To convert CMYK to RGB, use the following formulas:
	        - Red ® = 255 × (1 - C) × (1 - K)
	        - Green (G) = 255 × (1 - M) × (1 - K)
	        - Blue (B) = 255 × (1 - Y) × (1 - K)
	    - Here, C, M, Y, and K represent the CMYK values, and R, G, and B represent the RGB values.

> [!Question]
> Certainly! Let’s start by converting the RGB color `(122, 32, 244)` to CMYK and then back to RGB.
> 
> 1. **RGB to CMYK Conversion**:
>     - Normalize the RGB values by dividing each component by 255:
>         - Red ® = 122 / 255 ≈ 0.478
>         - Green (G) = 32 / 255 ≈ 0.125
>         - Blue (B) = 244 / 255 ≈ 0.957
>     - Calculate the CMYK values:
>         - Cyan © = 1 - R ≈ 0.522
>         - Magenta (M) = 1 - G ≈ 0.875
>         - Yellow (Y) = 1 - B ≈ 0.043
>         - Black (K) = min(C, M, Y) ≈ 0.043 (since Y is the smallest)
> 
> 1. **CMYK to RGB Conversion**:
>     - Use the following formulas:
>         - Red ® = 255 × (1 - C) × (1 - K) ≈ 122
>         - Green (G) = 255 × (1 - M) × (1 - K) ≈ 32
>         - Blue (B) = 255 × (1 - Y) × (1 - K) ≈ 244
> 

2. Elaborate why the conversion between CMYK and RGB and back again cannot expect identical values.
	- The RGB and CMYK color models have different gamuts (ranges of colors they can represent).
	- RGB can display more vibrant and saturated colors, especially in digital screens.
	- CMYK is optimized for printing, but it cannot reproduce all RGB colors accurately.
	- When converting from RGB to CMYK, some colors may be out of gamut (not representable in CMYK), leading to color shifts.
	- Similarly, converting from CMYK to RGB may result in loss of vibrancy due to the limited CMYK gamut.
	- Additionally, the black component (K) in CMYK is used to improve shadow details, but it doesn’t have a direct counterpart in RGB.
	- Therefore, achieving identical values between RGB and CMYK is challenging due to these inherent differences.

3. RGB to HSV Conversion:

> [!METHOD]
> **Normalize the RGB values**:
> 	Transform each component’s value (R, G, B) to a range of 0 to 1 by dividing each value by 255 (since the original range is 0-255).
> 
> **Find the minimum (min) and maximum (max) values** among R, G, and B.
> 
> **Calculate the hue (H)**:
> 	If `max` equals `min`, **set `H` to 0** (to avoid division by zero).
> 	Otherwise:
> 	If `max` is equal to `R`, calculate `H` as
> 	**60×(G−B/max−min​)**
> 	If `max` is equal to `G`, calculate `H` as
> 	**60×((B−R/max−min)​+2)**
> 	If `max` is equal to `B`, calculate `H` as
> 	**60×((R−G​/max−min)+4)**
> 
> **Calculate the saturation (S)**:
> 	If `max` is 0 (i.e., all RGB components are 0), set `S` to 0 (to avoid division by zero).
> 	Otherwise, calculate `S` as
> 	**max−min​/max**
> 
> **Calculate the value (V)**:
> 	**Set `V` to `max`.**

1. **HSV to RGB Conversion**:
    
    - Given the HSV values (H, S, V):
        - Normalize `H` to the range 0-360 (if needed).
        - Normalize `S` and `V` to the range 0-1 (if needed).
    - Calculate the intermediate values:
        - C=V×S
            
        - X=C×(1−∣(H/60)mod2−1∣)
            
        - m=V−C
            
    - Determine the RGB components:
        - If
            
            0≤H<60
            
            :
            
            R=C,G=X,B=0
            
        - If
            
            60≤H<120
            
            :
            
            R=X,G=C,B=0
            
        - If
            
            120≤H<180
            
            :
            
            R=0,G=C,B=X
            
        - If
            
            180≤H<240
            
            :
            
            R=0,G=X,B=C
            
        - If
            
            240≤H<300
            
            :
            
            R=X,G=0,B=C
            
        - If
            
            300≤H<360
            
            :
            
            R=C,G=0,B=X
            
    - Add the value offset:
        - R=R+m
            
        - G=G+m
            
        - B=B+m
            
    - Scale the RGB components to the 0-255 range:
        - R=round(255×R)
            
        - G=round(255×G)
            
        - B=round(255×B)
# Reference
![[Lecture3.pdf]]