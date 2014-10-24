voiture
=======
1)  Créer une classe package Car :
--------------------
attributs : 
private String name : le nom de la voiture
private int year : l’année de construction
private String state : l’état de la voiture

méthodes : 
public void start() : démarre la voiture -> state = “driving”
public void stop() : arrête la voiture -> state = “stopped”
public String describe() : renvoie un descriptif de la voiture en fonction de touts ses attributs

	accesseurs :
		générer des accesseurs public pour name et year, et protected pour state

	constructeur :
		Créer un constructeur par défaut qui affiche ”Default Car” et qui initialise year et name à l’aide de valeurs par défaut.

Tester la classe Car à l’aide d’un main dans une classe TestMain: 
	Car car = new Car();
System.out.println(car.describe());

Modifier la classe Car, passer la méthode describe en visibilité private
	Que se passe-t-il?

repasser la méthode describe en visibilité public

2) Créer une classe public SportsCar, qui hérite de Car
--------------------
	attributs :
private int nbCylinders : nombre de cylindres
	
méthodes : 
	redéfinir start() : state = “drive fast”;
	redéfinir describe() : appeler la méthode super, ajouter le nombre de cylindres au descriptif
	accesseurs :
		générer des accesseurs public pour nbCylinders
	constructeur :
		Créer un constructeur par défaut qui affiche “Sports Car” et qui initialise l’attribut nbCylinders

Tester la classe SportsCar à l’aide d’un main : 
	SportsCar sportsCar = new SportsCar();
System.out.println(sportsCar.describe());

Que se passe-t-il?
3) Modifications la classe Car 
--------------------
	- créer un package com.serli.vehicules
	- déplacer la classe Car dans com.serli.vehicules
	Que se passe-t-il?
	
	- déplacer la classe SportsCar dans le package com.serli.vehicules
	- modifier la visibilité de la classe Car en public
		
	- modifier le constructeur de la classe Car, créer un constructeur par arguments (year, name)
	Que se passe-t-il?
	Quelles sont les modifications envisagées?
4) Polymorphisme
--------------------
	Remplacer le constructeur par défaut de SportsCar par un constructeur par attributs (name, year, nbCylinders)

	Tester la classe SportsCar à l’aide d’un main : 
		Car car = new SportsCar(“Porshe”, 1995, 8);
System.out.println(car.describe());

Que se passe-t-il?
Quel est le type de la variable  “car”?
Que se passe-t-il si on appelle car.getNbCylinders()?
5) Classe abstraite : Vehicule
--------------------
	Créer un classe abstraite Vehicule.
	Faire hériter la classe Car de Vehicule.
	Remonter l’attribut state dans la classe Vehicule.
	Remonter la méthode stop dans la classe Vehicule.
Déclarer les méthodes describe et start vues précédemment en tant que méthodes abstraites.
Créer un constructeur par défaut qui affiche “Vehicule”
6) Enumération
--------------------
	Créer une énumération Propulsion qui contient les valeurs : SAIL, ENGINE
	Créer une classe Boat qui hérite de Vehicule
	
	attributs : 
	private Propulsion propulsion;
	private String name;
	private boolean anchored;
	méthodes :
		public void throwAnchor()
		public void weighAnchor()
	L’ancre doit être jetée et levée quand le bateau démarre ou s’arrête

	Tester cette classe à l’aide d’un main.
Que se passe-t-il?
	
7) Créer une interface CanPrintDescription
--------------------
méthode : 
void printDescription();

la classe Vehicule implémente désormais l’interface CanPrintDescription :
	public void printDescription() {
		System.out.println(describe());
	}

Créer une classe Sandwich qui implémente CanPrintDescription

Créer un main qui contient un tableau de CanPrintDescription : 
Remplir ce tableau à l’aide de :1 Car, 1 SportsCar, 1 Boat, 1 Sandwich
Afficher le contenu du tableau à l’aide d’une boucle en appelant la méthode printDescription()
Quel est l’intérêt de ce mode de fonctionnement?
8) Static
--------------------
- ajouter une variable public static int countInstances à la classe Vehicule, initialisée inline à 0;
- surcharger le constructeur afin qu’il incrémente la variable à chaque appel

Exécuter le code suivant : 
	Car car = new SportsCar();
	Car car2 = new SportsCar();
Car car3 = new SportsCar();
System.out.println(sportsCar.countInstances);
Que se passe-t-il?
9) final
--------------------
	ajouter final à la définition de la méthode start de la classe Car
	Que se passe-t-il?
