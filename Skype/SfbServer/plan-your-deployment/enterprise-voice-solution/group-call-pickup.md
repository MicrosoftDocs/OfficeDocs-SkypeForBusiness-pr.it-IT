---
title: Pianificare la risposta alle chiamate di gruppo in Skype for Business
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.collection:
  - IT_Skype16
  - Strat_SB_Admin
ms.custom: null
ms.assetid: 3dc0eca8-c773-463c-96bb-9cd6afa2a840
description: 'Pianificazione della risposta alle chiamate di gruppo in Skype for Business Server VoIP aziendale, che consente agli utenti di rispondere alle chiamate originariamente destinate ad altri utenti.'
---

# <a name="plan-for-group-call-pickup-in-skype-for-business"></a>Pianificare la risposta alle chiamate di gruppo in Skype for Business
 
Pianificazione della risposta alle chiamate di gruppo in Skype for Business Server VoIP aziendale, che consente agli utenti di rispondere alle chiamate originariamente destinate ad altri utenti.
  
La risposta alle chiamate di gruppo consente agli utenti di rispondere alle chiamate in arrivo ai propri colleghi dai propri telefoni. In questo modo si aumenta la disponibilità della linea di un utente consentendo ad altri utenti di rispondere a una chiamata in arrivo componendo un numero di gruppo di prelievo chiamata. Quando viene distribuito il prelievo delle chiamate di gruppo, il numero di chiamate in arrivo instradati alla segreteria telefonica può essere notevolmente ridotto, cosa particolarmente utile per le chiamate provenienti da clienti esterni all'organizzazione.
  
La funzionalità di prelievo delle chiamate di gruppo è progettata in particolare per le unità aziendali in ambienti open office. Le chiamate in arrivo non sono dirompenti perché squillano solo alla destinazione prevista. Altri utenti che ascoltano l'anello, tuttavia, possono comunque riprendere la chiamata semplicemente componendo il numero di gruppo. 
  
In ambienti in cui gli utenti non si trovano in un layout di ufficio aperto o in cui gli utenti che condividono una responsabilità comune sono distribuiti geograficamente, la chiamata al team presenta la soluzione più adatta. La differenza principale tra la risposta alle chiamate di gruppo e quella del team consiste nel fatto che, con la risposta alle chiamate di gruppo, una chiamata in arrivo squilla solo alla destinazione prevista, ma chiunque può comunque scegliere di rispondere componendo un numero di gruppo. Con la chiamata del team, la chiamata squilla a tutti i telefoni dei membri del team e qualsiasi utente del team può prendere il telefono per rispondere alla chiamata. Un'ulteriore differenza tra la risposta alle chiamate di gruppo e la chiamata al team è che la risposta alle chiamate di gruppo è gestita da un amministratore, tramite Skype for Business Server. Con la chiamata del team, gli utenti finali gestiscono la funzionalità utilizzando il client Skype for Business client. Con la risposta alle chiamate di gruppo, pertanto, questo aspetto della gestione delle chiamate può essere centralizzato.
  
La risposta alle chiamate di gruppo si basa sull'applicazione Parcheggio di chiamata. Quando si distribuisce la risposta alle chiamate di gruppo, si configura la tabella orbit del parcheggio di chiamata con intervalli separati di numeri di interno designati come numeri di gruppo di prelievo chiamata. Come i numeri orbit del parcheggio di chiamata, i numeri di gruppo di prelievo delle chiamate devono essere interni virtuali a cui non è assegnato alcun utente o telefono. Ogni pool Front End in cui si distribuisce la risposta alle chiamate di gruppo può avere uno o più intervalli di numeri di gruppo di prelievo chiamata. Gli intervalli di numeri di gruppo devono essere univoci a livello globale nella Skype for Business Server distribuzione. 
  
> [!NOTE]
> Gli intervalli di numeri designati come numeri di risposta alle chiamate di gruppo nella tabella orbit del parcheggio di chiamata non possono essere gestiti o visualizzati utilizzando il Pannello Skype for Business Server di controllo. L'unico modo per visualizzare tutti gli intervalli di numeri nella tabella orbit del parcheggio di chiamata è utilizzare Skype for Business Server Management Shell. Analogamente, l'unico modo per aggiungere, modificare o rimuovere i numeri di risposta alle chiamate di gruppo è utilizzare Skype for Business Server Management Shell. 
  
Dopo aver configurato i numeri del gruppo di prelievo delle chiamate, assegnare gli utenti a un gruppo di prelievo chiamata. Qualsiasi utente assegnato a un gruppo di prelievo delle chiamate può rispondere alle proprie chiamate da altri utenti. Quando una chiamata arriva a un utente assegnato a un gruppo di prelievo chiamata, qualsiasi altro utente che nota la chiamata può rispondere componendo manualmente il numero del gruppo di prelievo chiamata. L'utente che preleva la chiamata non deve essere un membro del gruppo. Quando una chiamata viene ritirata da un altro utente, viene inviata una notifica al numero originariamente chiamato.
  
> [!NOTE]
> Un utente può essere membro di un solo gruppo di prelievo chiamata. 
  
> [!NOTE]
> Anche se qualsiasi utente nella distribuzione di Skype for Business Server può rispondere a una chiamata a un membro del gruppo di prelievo chiamata, l'utente che risponde alla chiamata deve conoscere il numero di gruppo di prelievo della chiamata corretto da comporre. 
  
Se un utente compone un numero di gruppo di prelievo chiamata per rispondere a una chiamata quando squillano più telefoni del gruppo, l'utente risponde alla chiamata che squilla più a lungo.
  
Le impostazioni di squillo simultaneo funzionano per gli utenti che hanno la risposta alle chiamate di gruppo. In altre informazioni, una chiamata effettuata a un utente che dispone di risposta alle chiamate di gruppo squillerà per tutte le destinazioni configurate e un altro utente può rispondere alla chiamata. L'eccezione a questa regola è quando l'utente configura lo squillo simultaneo per chiamare tutti i membri del team.
  
La risposta alle chiamate di gruppo non può essere utilizzata per rispondere ai seguenti tipi di chiamate:
  
- Chiamate a una linea privata
    
- Chiamate da un contatto a cui è stata assegnata la relazione di privacy amici e familiari
    
    > [!TIP]
    > Un utente membro di un gruppo di prelievo delle chiamate può impedire il recupero di determinate chiamate tramite la risposta alle chiamate di gruppo contrassegnando il contatto come contatto personale nel client Skype for Business chiamata. Per contrassegnare un contatto come contatto personale, impostare la relazione di privacy per il contatto su Amici e familiari. Qualsiasi chiamata in arrivo dai contatti con la relazione di privacy impostata su Amici e famiglia non può essere recuperata utilizzando La risposta alle chiamate di gruppo. 
  
- Parte video delle chiamate audio/video 
    
    > [!NOTE]
    > Se un utente risponde a una chiamata audio/video, riceve solo l'audio. La persona che chiama o la persona che risponde alla chiamata può inoltrare la chiamata per aggiungere video. 
  
- Chiamate di squillo simultanee instradati ai membri delle chiamate del team
    
- Chiamate instradati a un delegato
    
- Chiamate instradati a un Response Group
    
I seguenti tipi di utenti non possono partecipare alla risposta alle chiamate di gruppo. Ciò significa che non devono essere inclusi in un gruppo di prelievo chiamata di gruppo e non possono raccogliere le chiamate per gli utenti che hanno la risposta alle chiamate di gruppo abilitata.
  
- Utenti ospitati online in una distribuzione ibrida
    
- Utenti non ospitati in un pool di Skype for Business Server 2015 o in un pool di Lync Server 2013 con aggiornamenti cumulativi per Lync Server 2013: febbraio 2013 in una distribuzione locale
    
Se nessuno risponde a una chiamata a un membro di un gruppo di prelievo chiamata, la chiamata viene instradata come specificato nelle impostazioni del client. In altri modi, la chiamata passa alla segreteria telefonica o viene inoltrata a una destinazione diversa, come specificato nelle impostazioni del client.
  
## <a name="deployment-and-requirements"></a>Distribuzione e requisiti

La risposta alle chiamate di gruppo viene distribuita automaticamente quando si distribuiscono VoIP aziendale e l'applicazione Parcheggio di chiamata. È possibile abilitare la risposta alle chiamate di gruppo configurando la tabella orbit del parcheggio di chiamata con intervalli separati di numeri designati come numeri di gruppo di prelievo chiamata e quindi assegnando agli utenti di chiamare i gruppi di prelievo e abilitando gli utenti per la risposta alle chiamate di gruppo.
  
## <a name="clients-supported-for-group-call-pickup"></a>Client supportati per la risposta alle chiamate di gruppo

È possibile utilizzare uno dei client seguenti per rispondere alle chiamate ai membri di Group Call Pickup:
  
- Skype for Business
    
- Lync 2013
    
- Lync 2010
    
- Lync Phone Edition
    
> [!NOTE]
> Gli utenti possono utilizzare uno di questi client per rispondere alle chiamate ai membri di Prelievo chiamata di gruppo, ma gli utenti devono essere ospitati in un pool di Skype for Business Server o in un pool di Lync Server 2013 con aggiornamenti cumulativi per Lync Server 2013: febbraio 2013. 
  
I client e i dispositivi seguenti non sono supportati per la raccolta delle chiamate ai membri di Group Call Pickup:
  
- Lync Mobile
    
- App Lync per Windows 8 e Windows RT
    
- Lync per iPad
    
- Telefoni analogici
    
- Telefoni con numeri PSTN (Public Switched Telephone Network)
    
## <a name="capacity-planning"></a>Pianificazione della capacità

Nella tabella seguente viene descritto il modello utente Di prelievo chiamata di gruppo che è possibile utilizzare come base per i requisiti di pianificazione della capacità.
  
> [!IMPORTANT]
> La risposta alle chiamate di gruppo si basa sull'applicazione Parcheggio di chiamata. Tenere presente che, per la pianificazione della capacità di ripristino di emergenza, ogni pool di un pool associato deve essere in grado di gestire i carichi di lavoro per i servizi parcheggio di chiamata, incluso il prelievo delle chiamate di gruppo, in entrambi i pool. 
  
**Modello utente di prelievo chiamata di gruppo**

|**Metrica**|**Per pool  <br/>  Front End (con 8 Front End Server)**|**Per server Standard Edition**|
|:-----|:-----|:-----|
|Numero consigliato di utenti per gruppo  <br/> |50  <br/> |50  <br/> |
|Numero consigliato di gruppi  <br/> |500  <br/> |60  <br/> |
|Numero massimo di utenti per pool abilitato per la risposta alle chiamate di gruppo  <br/> |25.000  <br/> |3,000  <br/> |
|Frequenza massima di chiamate in arrivo per il totale di utenti abilitati per il prelievo delle chiamate di gruppo per pool al minuto  <br/> |500  <br/> |60  <br/> |
|Frequenza massima di chiamate recuperate dagli utenti con prelievo chiamate di gruppo per pool al minuto  <br/> |200  <br/> |25  <br/> |
   
> [!NOTE]
> Per i pool Front End con meno di otto Front End Server, calcolare le metriche in modo lineare. Ad esempio, se il pool Front End dispone di un Front End Server, calcolare il carico massimo come 1/8 dei valori riportati nella tabella. 
  
> [!NOTE]
> È possibile aumentare o ridurre il numero consigliato di utenti per gruppo e il numero di gruppi purché non si superi il numero massimo di utenti per pool. Ad esempio, il server edizione Standard può avere 120 gruppi con 25 utenti per gruppo perché il numero di utenti abilitati per la risposta alle chiamate di gruppo è ancora compreso nel modello di utente massimo (ovvero, 120 gruppi per 25 utenti è 3.000 utenti abilitati per la risposta alle chiamate di gruppo). 
  

