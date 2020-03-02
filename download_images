wget "https://www.wikiart.org/en/App/Painting/PaintingsByArtist?artistUrl=norman-rockwell&json=2" -O rockwell.json

jq ".[].image" rockwell.json | tr -d \" > links

for i in {0..232}
do
	url=$(sed "${i}q;d" links)
	url=${url%\!Large.jpg}
	
	cd ./images
	wget $url 
	cd ../

	sleep 10
done

