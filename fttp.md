title: Fibre to the premisis (fttc) 
published: false
description: How telesur makes up the new fttp network in SR/SA
tags: #fttc #fttp #BPON #MSAN
--

 Ik heb _**veel en diepgaand**_ gelezen in de docs v/h fiber network van $rnet / SR. de **MSAN's** hebben o.a de oude DSLAM's in de server rooms vervangen. De _**multi-service access node**_ zorgt ook voor redundancy en kostenbesparing aangezien alles van POTS daar wordt gedigitized, in IP mode word omgezet en vervolgens over het grote ATM network naar de servers wordt gesmeten.

 Daarom is alles uitgevallen toen vandalen de dure apparatuur ergens uit een MSAN hadden gesloopt. Nu gaat dat moelijker door de verscherpte remote security van $rnet

 Echter hebben ze de omgeving nog steeds geen home-passed phase gegeven in phase-2 van het FTTH traject, terwijl ik jongens van MES heb gezien helemaal op Tamanredjo, toen ik daar trainde. We zien ook bij het block van DSB gravenstraat geen Fibre Access Terminals (was-wasi-godo's) in de EBS masten

**UPDATE**

Er worden nieuwe masten gezet in de buurt door de EBS. Daarom kregen we hier geen home passed FAT terminals in de masten.


**UPDATE-II**

Een maand daarna nog steeds geen **fat-terminals** in de straat

**UPDATE-III**

Maanden daarna _(dec-2019)_ nog steeds geen FAT terminals in de buurt / straat.


 Het is alsof de binnenstad een stiefmoederlijk treatment krijgt. Zijn de FAT terminals al aan de Kasabaholo weg? Ik heb niet opgelet toen ik daar voor het laatst trainde

 Nu weet ik ook dat we gaan van de _**FAT**_ op straat naar een ATB access terminal box binnen, die de fibre optic line netjes moet mounten in huis. Daarnaa gan we naar een Optical Network Terminal unit, welke volgens de #RFC  op https://tools.ietf.org/html/rfc6934 zorgt voor de koppeling van CU to fibre

 In de RFC is FTTP equivalent aan FTTH. Volgens deze RFC had $rnet ons VDSL kunnen bieden middels FTTC omdat er slechts een last mile over CU zou zijn, Daarvoor moet de CU cable echter goed zijn. De onze lekt al meer dan 20 jaar water(damp)

 Middels **BPON _(broadband passive optical network)_** kan $rnet ons 2.4GBit/s downstream leveren. Daarnaast is er ook XGPON welke genoeg is om 4K TV over fibre thuis te leveren. XGPon doet 10GBit/s downstream. Geen antennas dan meer. De zenders hebben gewoon (dure) network hardware aan het end welke gaat naar hun veel snellere TV' station grade Fibre link met de ISP

 Wanneer het **FTTP _(fibre to the premises)_** network af is met de koppeling van alle huizen kan $rnet starten met HQ triple play services zoals beschreven in de RFC met zowel unicast- als multicast-video VOIP & data. Ze gaan natuurlijk QoS draaien zodat de POTS calls bandwidth guarantee hebben, terwijl *cast video ook wordt gelimiteerd als het te gierig wordt voor bandbreedte.

 Het netwerk heet trouwens Passive omdat de splitters voor het optical signal unpowered zijn. 32 tot 128 nodes kunnen op de zelfde PON zitten
Per RFC => A PON configuration
consists of an Optical Line Terminal (OLT) at the service
provider's central office (CO) and a number f Optical Network
Units or Terminals (ONUs/ONTs) near end users, with an Optical
Distribution Network (ODN) composed of fibers and splitters between them.

A PON configuration reduces the amount of fiber and CO equipment required compared with point-to-point architectures.


 GPON is 2.4GBit/s BTW - BPON is 622MBit/s 

 Ik lees nu tussen de regels door. $rnet is op ATM welke is gelimiteerd op 622MBit/s Ze gaan ons dus met die network infrastructure nooit 10GBit/s kunnen leveren (de rijke companies dus, geen end users)
#
 We zullen dus een fractie van BPON krijgen als end users, maybe 100MBit/s max down. Ik moet nog studeren om te zien wat de upstream limits zijn
#
 Trouwens, $rnet wil ook TV over het netwerk bieden. Er is op ATM niet eens plaats voor 1080P resolution voor alle abonnees die op een FAT zijn aangesloten. Ik durf daarom te beweren dat ze intern al moeten zijn overgeschakeld naar een higher grade netwerk dan Asynchronous Transfer Mode omdat het onmogelijk lijkt te zijn met server houses die maximaal met 622MBit/s data naar elkaar kunnen gooien.
#
#BTW voor de homegateways is dit nog belangrijk voor end-user inspectie van het werk na oplevering door de contractor 

#  => RFC6934: 4.1.1.  Home Gateway

   The Home Gateway (HGW) connects the different CPEs to the ANX and the
   access network.  In the case of PON, the HGW is a Layer 3 router.  In
   this case, the HGW performs IP configuration of devices within the
   home via DHCP and performs Network Address and Port Translation
   (NAPT) between the LAN and WAN side.  In the case of FTTP/B/C, the
   HGW connects to the ONT/ONU over an Ethernet interface.  That
   Ethernet interface could be over an othernet physical port or over
   another medium.  In the case of FTTP, it is possible to have a single
   box GPON CPE solution where the ONT encompasses the HGW functionality
   as well as the GPON adaptation function. (edited)

# Ik heb het antwoord al. Het ATM netwerk is ATM layer 5

 RFC quote => 4.1.2.  PON Access

   PON access is composed of the ONT/ONU and OLT.  PON ensures physical
   connectivity between the ONT/ONU at the customer premises and the
   OLT.  PON framing can be BPON or GPON.  The protocol encapsulation on

BPON is based on multi-protocol encapsulation over ATM Adaptation
   Layer 5 (AAL5), defined in [RFC2684].  This covers PPP over Ethernet
   (PPPoE, defined in [RFC2516]) or IP over Ethernet (IPoE).  The
   protocol encapsulation on GPON is always IPoE.  In all cases, the
   connection between the AN (OLT) and the NAS (or BNG) is assumed to be
   Ethernet in this document.


#
#
