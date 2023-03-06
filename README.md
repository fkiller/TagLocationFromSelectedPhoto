# Tag Location From Selected Photos

TagLocationFromSelectedPhotos (such a long name) is a quick action made by Automator to automate estimating location of photos by geolocated photos taken before/after the photo. Use case is that you have a iPhone taking photos with GPS locations and a DSLR camera that doesn't have GPS feature at the same time.

https://user-images.githubusercontent.com/935034/223217533-d68642bf-ebbf-48b8-be92-205f6fac1729.mov

## Installation

1. Clone this repository.
2. Copy Tag Location From Selected Photos.workflow to **/Users/[current user]/Library/Services**
 
## How it works

1. Open Photos app
2. Make sure your photos are imported to Photos Library (It supports iCloud Photo Library)
3. Select Photos which also include geo-located photos at the begining and the end so any photos in-between could get locations based on the begining and the end
4. It's fine mixing geo-located photos and non-geo-located photos unless the beginning and the end photos have location meta data
5. Location is calculated as below
> $$ Location_{current} = Location_{before}+{{Location_{after}-Location_{before}} \over {DateTime_{after}-DateTime_{before}}} \times (DateTime_{current}-DateTime_{before})$$ 