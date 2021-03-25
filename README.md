# OEFENING ELEKTRISCHE TOESTELLEN  
### oefening op entiteitsklassen en serviceklassen  

We houden de voorraad van een winkel die elektro verkoopt bij.  
De winkel verkoopt verschillende soorten toestellen : Vaatwas, Oven, Wasmachine, Droogkast, Koelkast, Diepvries.  
Deze soorten dien je in de vorm van een enumaratie (Toestelsoorten) bij te houden (dus geen afzonderlijke entiteitsklasse).  Je kan deze enum best aanmaken in hetzelfde bestand waar je de klasse Toestel zal maken (zie hieronder) (onder "namespace", boven "class").  

### De entiteistklasse  (Toestel)
Van elk toestel houden we volgende zaken bij :    
  * Merk : tekst.  Indien leeg, automatisch de tekst "Onbekend merk" invullen.  
  * Serie : tekst.  Indien leeg, automatisch de tekst "Onbekende serie" invullen.  
  * Soort : enumeratie-type Toestelsoorten  
  * Verkoopprijs : indien kleiner dan 0, automatisch 0 laten invullen.  
  * Voorraad : indien kleiner dan 0, automatisch 0 laten invullen.   
  * Watt : geheel getal waarvan de waarde tussen 0 en 5000 moet liggen (automatisch aanpassen indien waarde kleiner of groter is)  
  * Voltage : geheel getal waarvan de waarde tussen 110 en 400 moet liggen (automatisch aanpassen indien waarde kleiner of groter is)  
  * Ampere : read-only eigenschap dat een berekende waarde aanbiedt (wattage/voltage)  

De klasse heeft 2 constructors
  * Een argumentloze
  * Een constructor die evenveel argumenten heeft als er eigenschappen dienen ingevuld te worden.

De klasse overschrijft de ToString() methode (merk en serie).  

### De Serviceklasse  (ToestelService)    
De service klasse heeft 3 eigenschappen :   
  * een List van toestellen  
  * het totaal aantal toestellen in de winkel  
  * de totale verkoopswaarde van alle aanwezige toestellen  
De klasse heeft 1 argumentloze constructor waarin je voor wat testgegevens (seeding) zorgt.  
De klasse heeft 3 publieke methoden :  
  * Een methode om een object toe te voegen aan de List  
  * Een methode om een object te verwijderen uit de List  
  * (maak dit eventueel wanneer je klaar bent met de rest) Een methode die een List van toestellen retourneert die van een bepaalde soort zijn : uiteraard wordt deze soort als argument ontvangen (dus enkel ovens, enkel diepvriezen ...)  
  
### De code behind  
Bekijk de demo om te weten wat er precies dient te gebeuren in je code behind.  
Maak eerst je programma zonder aan de filter te denken, en implementeer deze wanneer de rest van je programma klaar is.  
  
Er zijn 2 comboboxen op je scherm : cmbFilter en cmbSoort.  
  * CmbSoort dient gevuld te worden met de enumeratie waarden Toestelsoorten.  Je kan dit doen door de versillende enum waarden één voor één toe te voegen aan je combobox maar je kan dit ook doen met een iteratie :   
            foreach (ToestelSoort toestelsoort in Enum.GetValues(typeof(ToestelSoort)))
            {
                cmbSoort.Items.Add(toestelsoort);
            }
  * Bij cmbFilter kan je iets gelijkaardigs doen, maar je moet als eerste waarde in de combobox de tekst "<alle toestellen>" invoegen.  
    Het is echter geen probleem om de verschillende items van een combobox te vullen met verschillende types (dus hier tekst en enumeratietypes)


  


