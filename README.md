ec2imgutils
===========

A collection of utilities for image management in AWS EC2

Utilities:

# ec2deprecateimg

A command line utility to deprecate images in Amazon EC2. The platform does
not support a formal deprecation mechanism. The mechansim implemented by this
tool is a convention. Unfortunately the tags are not sticky, i.e. not visible
to others if the image is shared.

Images are tagged with:

- Deprecated on -> today's date in YYYYMMDD format
- Removal date -> today's date plus the deprecation period specified
- Replacement image -> The AMI ID and name of the replacement image

The image set as the replacement is removed from the list of potential
images to be deprecated before any matching takes place. Therefore, the
deprecation search criteria specified with _--image-name-frag_ or
_--image-name-match_ cannot match the replacement image.


# ec2publishimg


A command line utility to control the visibility of an image in AWS EC2.
The tool supports setting an image to public or private.


## Installation

### openSUSE and SUSE Linux Enterprise

```
zypper in python3-ec2imgutils
```


## Usage

```
ec2deprecateimg --account example --image-name-match v15 --image-virt-type hvm --replacement-name exampleimage_v16
```

See the [man page](man/man1/ec2deprecateimg.1) for more information.

```
man ec2deprecateimg
```

