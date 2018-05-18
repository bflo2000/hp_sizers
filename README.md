# BMW Utilities
Amazon Sizer and Validator for Historic Pictoric

### Log:
 -5/19 Added collection and root sku to validator and sizer.
- 5/17 Added deque to validator.
- 5/07 Changed 3:2 grouping to 1.39 and above, as opposed to 1.415.
- 4/26 Changed map sizing to scale with the natural ratio for 44 sizes.
- 4/25 Changed bullets according to standard sizes
- 4/17 Removed 16x20 item sizes for maps
- 4/15 Created Validator

---------------------------------------------------------------------------------
To run sizer:

From within the sizer directory, run this command from the terminal:

python sizer.py FILENAME.csv options

FILENAME being the name of the csv file you wish to process.

The file created will be outputted as "AMZ_' + input_filename + '_' + ("%m_%d_%Y") + '.csv"

---------------------------------------------------------------------------------

To run validator:

python validator.py FILENAME.csv options

FILENAME being the name of the csv file you wish to process.

The validator outputs three files:

- 'AMZ_' + input_name + '_' + ("%m_%d_%Y") + '.csv'
- 'AMZ_' + input_name + '_' + ("%m_%d_%Y") + '_delete.csv'
- 'AMZ_' + input_name + '_' + ("%m_%d_%Y") + '_price.csv'

---------------------------------------------------------------------------------

**options** is an integer representing the longest side of the sizes you wish to generate.

If no value is specified for options, then all sizes will be generated.

---------------------------------------------------------------------------------

The CSV's fields must be formatted according to the schema below:

item_sku **OR** Sku **OR** SKU 

image_name **OR** name **OR** Image_Name **OR** name

image_height **OR** height

image_width **OR** width

kind **OR** Kind **OR** category:
	
item_name **OR** Title **OR** title

product_description **OR** product description

keywords **OR** Keywords

image_folder **OR** ImageFolder

** When using the validator, include is_parent. The data must be retrieved from the most recent database**

---------------------------------------------------------------------------------

Constraints:

Title must be <= 188 characters.

Use 'photos', 'photo', 'Photograph', or 'photograph' for the field value.
---------------------------------------------------------------------------------

#### Photo/print sizing:

	if ratio less 1.1:
		12 x 12
		16 x 16
		24 x 24
		36 x 36

	ratio between 1.1 and 1.3:
		8 x 10
		11 x 14
		16 x 20
		18 x 24
		24 x 30
		32 x 44
		44 x 55

	ratio between 1.3 and 1.39:
		8 x 10
		11 x 14
		16 x 20
		18 x 24
		24 x 30
		32 x 44
		44 x 60

	ratio between 1.39 and 1.9:
		8 x 12
		16 x 24
		24 x 36
		30 x 44
		44 x 66

	 ratio between 1.9 and 3.0:
		16 x 32
		20 x 40
		24 x 48
		44 x 88

---------------------------------------------------------------------------------
#### Map sizing:

For maps, the ratio is rounded to one of the ratios below.

	if ratio = 1.0:
		12 x 12
		16 x 16
		24 x 24
		36 x 36
		44 x 44

	if ratio == 1.1:
		16 x 18
		22 x 24
		32 x 36
		40 x 40
		44 x 49

	if ratio == 1.25:
		18 x 24
		24 x 30
		32 x 44
		44 x 55

	if ratio == 1.33:
		18 x 24
		24 x 32
		32 x 44
		44 x 60

	if ratio == 1.5:
		16 x 24
		24 x 32
		30 x 44
		44 x 66

	if ratio == 2.0:
		16 x 32
		20 x 40
		24 x 48
		44 x 88

---------------------------------------------------------------------------------

#### Pricing Table:

	square_inches < 299:
		price = 29.99
	 square_inches >= 300 and square_inches <= 399:
		price = 39.99
	 square_inches >= 400 and square_inches <= 499:
		price = 49.99
	 square_inches >= 500 and square_inches <= 599:
		price = 54.99
	 square_inches >= 600 and square_inches <= 699:
		price = 59.99
	 square_inches >= 700 and square_inches <= 799:
		price = 64.99
	 square_inches >= 800 and square_inches <= 899:
		price = 69.99	
	 square_inches >= 900 and square_inches <= 999:
		price = 74.99
	 square_inches >= 1000 and square_inches <= 1099:
		price = 79.99
	 square_inches >= 1100 and square_inches <= 1199:
		price = 84.99
	 square_inches >= 1200 and square_inches <= 1299:
		price = 89.99
	 square_inches >= 1300 and square_inches <= 1399:
		price = 94.99	
	 square_inches >= 1400 and square_inches <= 1499:
		price = 99.99	
	 square_inches >= 1500 and square_inches <= 1599:
		price = 149.99
	 square_inches >= 1600 and square_inches <= 1699:
		price = 159.99
	 square_inches >= 1700 and square_inches <= 1799:
		price = 169.99
	 square_inches >= 1800 and square_inches <= 1899:
		price = 179.99
	 square_inches >= 1900 and square_inches <= 1999:
		price = 189.99
	 square_inches >= 2000 and square_inches <= 2099:
		price = 199.99
	 square_inches >= 2100 and square_inches <= 2199:
		price = 209.99
	 square_inches >= 2200 and square_inches <= 2299:
		price = 219.99
	 square_inches >= 2300 and square_inches <= 2399:
		price = 229.99
	 square_inches >= 2400 and square_inches <= 2499:
		price = 239.99
	 square_inches >= 2500 and square_inches <= 2599:
		price = 249.99
	 square_inches >= 2600 and square_inches <= 2699:
		price = 259.99
	 square_inches >= 2700 and square_inches <= 2799:
		price = 269.99
	 square_inches >= 2800 and square_inches <= 2899:
		price = 279.99
	 square_inches >= 2900 and square_inches <= 2999:
		price = 289.99
	 square_inches >= 3000 and square_inches <= 3099:
		price = 299.99
	 square_inches >= 3100 and square_inches <= 3199:
		price = 309.99
	 square_inches >= 3200 and square_inches <= 3299:
		price = 319.99
	 square_inches >= 3300 and square_inches <= 3399:
		price = 329.99
	 square_inches >= 3400 and square_inches <= 3499:
		price = 339.99
	 square_inches >= 3500 and square_inches <= 3599:
		price = 349.99
	 square_inches >= 3600 and square_inches <= 3699:
		price = 359.99
	 square_inches >= 3700 and square_inches <= 3799:
		price = 369.99
	 square_inches >= 3800 and square_inches <= 3899:
		price = 379.99
	 square_inches >= 3900 and square_inches <= 3999:
		price = 389.99
	 square_inches >= 4000 and square_inches <= 4099:
		price = 399.99
	 square_inches >= 4100 and square_inches <= 4199:
		price = 409.99
	else:
		price = 419.99
