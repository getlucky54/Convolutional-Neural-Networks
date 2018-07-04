# Convolutional-Neural-Networks
Detektovanje macke ili psa na slikama koristeci Konvolucionu neuralnu mrezu (Convolutional Neural Networks) u TensorFlow okruzenju
U ovom dokumentu implementiran je kod koji detektuje macku ili psa gde je koriscena CNN neuralna mreza. Set podataka koji je koriscen preuzet je sa Kaggle sajta (https://www.kaggle.com/c/dogs-vs-cats). Set podataka pomocu kojih je mreza trenirana sadrzi 25000 labelisanih slika, i 12500 slika za testiranje. 
U prvom delu koda napravljena je funkcija (def create_label) koja kodira labelisane slike. Zatim su napravljene funkcije za ucitavanje slika za treniranje i slika pomocu koji ce se mreza testirati (def create_train_data , def create_test_data). Ove dve funkcije ucitavaju slike kao GRAYSCALE i menjaju velicinu slike na velicinu 120x120. Takodje, zapisuju slike u niz u .npy file-u.
Nakon ucitavnja podataka, napravljen je model konvolucione neuralne mreze. Konvolucione neuronske mreze sastoje se od neurona koji imaju tezinske koeficijente koje treba obuciti. Svaki neuron prihvata neke ulazne informacije, primenjuje skalarni proizvod i propusta izlaz
kroz nelinearnu funkciju. Slojevi konvolucione mreze imaju neurone struktuirane u 3 dimenzije, to su:sirina, visina, dubina (width, height, depth). Neuroni u sloju povezani su sa malim regionom na prethodnom sloju, umesto sa svim neuronima. Struktura neuronske mreze:
1. Ulaz (input) – vrednosti piksela na slici u kanalima;

2. Konvolucioni sloj (CONV) – racuna izlaze neurona koji su povezani sa lokalnim regionima na ulazu, za svaki se racuna skalarni proizvod izmedju tezinskog koeficijenta i regiona sa kojim je povezan na ulazu. Biramo koliko zelimo razlicitih filtera da koristimo kao izlaz.

3.RELU sloj – primenjuje funkciju aktivacije;

4.POOL sloj ce primeniti skaliranje u prostornom smislu – npr. ako je ulaz bio dimenzija [32, 32, 6], izlaz ce biti [16, 16, 6].

5.FC (fully connected) sloj - predstavlja deo u konvolucionoj mrezi koji je isti kao klasicna neuronska mreza.
Na kraju je uradjena provera, gde se nasumicno odabrane slike stavljaju u tabelu i oznacavaju sa imenom "Cat" ukoliko je na slici macka, a sa imenom "Dog" ukoliko je na slici pas.
