v # m3-uf1-exc2
## Exercici 2: Blocs de codi, àmbits de variables, estructures bàsiques de control de fluxe i funcions.

En aquest exercici haureu de respondre les següents preguntes, substituint allà on posi //TODO per la vostra resposta.

Haureu d'utilitzar el jshell per a testejar tot el codi relacionat amb cada pregunta, i al final de l'exercici haureu d'incloure en aquest repositori els fitxers _history_ i _snippets_ (seguint el patró de noms establert a l'exercici 0) corresponents a aquest exercici, **directament al directori arrel del repositori**.

### Criteris de qualificació:
* Si no s'incorporen els fitxers _history_ i _snippets_ amb els seus continguts que demostrin que l'alumne ha treballat en les respostes a cadascuna de les preguntes, la qualificació serà de 0.
* Cada pregunta val dos punts, i la seva qualificació podrà ser de 0, 1 o 2, depenent de si la resposta és errònia o molt poc encertada (0), si és parcialment correcte (0.5) o de si és totalment correcte (1).
* Hi ha 5 preguntes, i la qualificació mínima per a superar aquest exercici és de 5/10.
* S'avaluarà la correctesa en la resposta, així com la seva **claredat** (que no presenti ambigüitats).
* Tot i que l'enunciat està redactat en català, l'alumne pot respondre, a banda de en català, en anglès o en espanyol. Faltes d'ortografia en el redactat penalitzarà la nota.

### Preguntes

#### Pregunta 1 - Números primers

Escriu una funció, la signatura de la qual serà

```
void isPrime(int n);
```

que imprimeixi _true_ si n és un número primer positiu, o _false_ si n és un número no primer o bé és 0, o bé és un enter negatiu.

Escriu aquesta funció a continuació:

//TODO
	void isPrime(int n) {
		boolean primo = true;
		int contador = 2;
		if(n<=1){
			primo=false;
		}	
		else {
			while ((primo) && (contador!=n)){
				if (n % contador == 0)
					primo = false;
				contador++;
			}
		}
		println(primo);
	}


Ara, escriu una altra funció, que tindrà per signatura:

```
void findPrimes(int a, int b);
```
que donat un rang [a,b] de números enters, imprimeixi per pantalla aquells números que siguin primers i positius.
Aquesta funció hauria de fer ús de la funció anterior _isPrime(int n)_, de la qual n'hauràs de fer un _override_ per 
a adaptar-la als requeriments de la funció _findPrimes_ (és a dir, la primera funció imprimeix _true_ o _false_, 
mentre que la segona funció imprimeix els números en sí mateixos però només si compleixen la condició -que sigui 
primer i positiu-).

//TODO (overriding de la funció _isPrime_)
	boolean isPrime(int n) {
		boolean primo = true;
		int contador = 2;
		if(n<=1){
			primo=false;
		}	
		else {
			while ((primo) && (contador!=n)){
				if (n % contador == 0)
					primo = false;
				contador++;
			}
		}
		return primo;
	}


//TODO (funció _findPrimes_)
	void findPrimes(int a, int b) {
		while(a<=b) {
			if(isPrime(a))
				println(a);
			a++;
		}
	}


#### Pregunta 2 - Màxim comú divisor

En aquest exercici has de crear una funció que retorni el GCD (_Greatest Common Divisor_ - o Màxim Comú Divisor) de dos enters
positius donats:

```
int gcd(int n, int m);
```
Per a resoldre aquest problema heu d'implementar amb Java l'**algorisme d'Euclides**.
Trobareu informació i exemples sobre aquest algorisme a:

Escriu a continuació la funció _gcd_:

//TODO 
	int gcd(int n, int m){
	    while(m != 0){
	         int t = m;
	         m = n % m;
	         n = t;
	    }
	    return n;
	}


#### Pregunta 3 - Recursivitat

Escriu una funció, amb la següent signatura, que calculi i retorni el factorial d'un número enter positiu donat:

```
int factorial(int n);
```

Aquesta funció ha de retornar -1 sempre que el valor del paràmetre n sigui un número negatiu.

Aquesta funció ha de fer ús del concepte de recursivitat.

Escriu el cos de la funció a continuació:

//TODO
	int factorial(int n){
		if(n<0)
			return -1;
	    if(n==0)
	        return 1;
	    else
	    	return n * factorial(n-1);
	}


#### Pregunta 4

4.1- Si volem consultar el número d'iteracions que un bucle ha fet quan ha acabat, quina estructura de control de fluxe utilitzarem,
un _while_ o un _for_? Per què?

//TODO Resposta aquí
Utilitzem el for perque es una estructura iterativa que s'executa un nombre preestablert de vegades, que és controlat per un comptador o índex, incrementat en cada iteració.

4.2- Què és un bloc de codi anònim? Posa un exemple útil.

//TODO Resposta aquí (explicació i exemple)
Els blocs de codi anònims son una secció de codi amb una o més declaracions i sentències. Un llenguatge de programació que permet blocs, incloent blocs niats dins d'altres blocs és anomenat un llenguatge de programació estructurat per blocs.
"public static void main(String[] args) { // in { // out } }"

4.3- Explica per què serveix una variable anomenada _found_ de tipus booleà, que se sol utilitzar quan programem bucles.
Posa almenys un exemple original teu i que no haguem vist a classe.

//TODO Resposta aquí (explicació i exemple)

El found es una funcio que indica el element per trobarlo

4.4- Explica amb exemples la diferència entre fer un _overriding_ de funcions o fer-ne un _overloading_.

//TODO Resposta aquí (explicació i exemples)
Un _overriding_ consiste en reescri   bir una funcion con la misma firma con el fin de substituir su contenido.
Un _overloading_ consiste en modificar el valor de las variables en la firma para tener dos funciones con el mismo contenido(o no) y con el mismo nombre.


#### Pregunta 5

Escriu una funció que, donada una seqüència de números enters entre el 65 i el 90 (inclosos), t'imprimeixi per pantalla la seqüència 
corresponent de caràcters segons la codificació estàndard Unicode.

La signatura d'aquesta funció serà:

```
void printChars(int a, int ... b);
```
Aquesta funció ha d'imprimir el següent missatge d'error si algun dels enters està fora del rang [65,90]:

```
Error: Enter fora del rang [65,90]
```

Escriu la funció a continuació:

//TODO
void printChars(int a, int ... b){
	for(int i:b){
		if(i >= 65 && i <= 90){
			println((char)(i));
		} else {
			println("Error: numero fora de rang.");
		}	
	}
}
	

**Hints**:
Per a recórrer tots els enters introduits com a paràmetres, has d'usar una variant del _for_ anomenada _foreach_, de la qual 
teniu un exemple a continuació:
```
for (int i: b) print(i);
```
(essent b el paràmetre varargs). Nota: tot i que aquesta variant es diu _foreach_, se segueix utlitzant la paraula clau _for_.

Per a imprimir una cadena de text, heu d'escriure el literal entre cometes dobles. Exemple:
```
println("Cadena de texte");
```



             


