---
title: Pianificare il ritiro delle chiamate di gruppo in Skype for business
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 3dc0eca8-c773-463c-96bb-9cd6afa2a840
description: Pianificazione del ritiro delle chiamate di gruppo in Skype for Business Server VoIP aziendale, che consente agli utenti di rispondere alle chiamate originariamente destinate ad altri.
ms.openlocfilehash: 874b9385352a8c51d9c9a356dd0ccc2ca3070601
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825616"
---
# <a name="plan-for-group-call-pickup-in-skype-for-business"></a>Pianificare il ritiro delle chiamate di gruppo in Skype for business
 
Pianificazione del ritiro delle chiamate di gruppo in Skype for Business Server VoIP aziendale, che consente agli utenti di rispondere alle chiamate originariamente destinate ad altri.
  
Il prelievo delle chiamate di gruppo consente agli utenti di rispondere alle chiamate in arrivo ai propri colleghi tramite i propri telefoni. In questo modo si aumenta la disponibilità della linea di un utente, consentendo ad altri utenti di rispondere a una chiamata in arrivo componendo un numero di gruppo di prelievo di chiamata. Quando viene distribuito il prelievo delle chiamate di gruppo, il numero di chiamate in arrivo instradate alla segreteria telefonica può essere ridotto significativamente, il che è particolarmente utile per le chiamate provenienti da clienti esterni all'organizzazione.
  
La funzionalità di prelievo delle chiamate di gruppo è stata progettata in particolare per le unità aziendali in ambienti Office aperti. Le chiamate in arrivo non sono di disturbo perché squillano solo nella destinazione prevista. Tuttavia, gli altri utenti che ascoltano l'anello possono comunque prendere la chiamata semplicemente componendo il numero del gruppo. 
  
Negli ambienti in cui gli utenti non sono ubicati in un layout Open Office o in cui gli utenti che condividono una responsabilità comune sono distribuiti geograficamente, il team Call presenta la soluzione più adatta. La differenza principale tra il prelievo di chiamate di gruppo e la chiamata del team consiste nel fatto che, con il prelievo delle chiamate di gruppo, una chiamata in arrivo squilla solo nella destinazione prevista, ma chiunque può comunque scegliere di rispondere componendo un numero di gruppo. Con il team di chiamata, la chiamata squilla a tutti i telefoni dei membri del team e tutti gli utenti del team possono prendere il telefono per rispondere alla chiamata. Un'ulteriore differenza tra il prelievo di chiamate di gruppo e la chiamata del team è che il prelievo delle chiamate di gruppo è gestito da un amministratore, tramite Skype for Business Server. Con la chiamata del team, gli utenti finali gestiscono la funzionalità utilizzando il client Skype for business. Con il prelievo delle chiamate di gruppo, pertanto, questo aspetto della gestione delle chiamate può essere centralizzato.
  
Il prelievo delle chiamate di gruppo è basato sull'applicazione Parcheggio di chiamata. Quando si distribuisce il prelievo delle chiamate di gruppo, è possibile configurare la tabella orbit del parcheggio di chiamata con intervalli distinti di numeri di interno designati come numeri del gruppo di prelievo delle chiamate. Analogamente ai numeri dell'orbita del parcheggio di chiamata, i numeri del gruppo di prelievo delle chiamate devono essere estensioni virtuali a cui non è assegnato alcun utente o telefono. Ogni pool Front end in cui si distribuisce il prelievo delle chiamate di gruppo può avere uno o più intervalli di numeri del gruppo di prelievo delle chiamate. Gli intervalli di numeri di gruppo devono essere univoci a livello globale nella distribuzione di Skype for Business Server. 
  
> [!NOTE]
> Gli intervalli di numeri designati come numeri di prelievo delle chiamate di gruppo nella tabella di orbit del parcheggio di chiamata non possono essere gestiti o visualizzati utilizzando il pannello di controllo di Skype for Business Server. L'unico modo per vedere tutti gli intervalli di numeri nella tabella di orbit del parcheggio di chiamata è l'utilizzo di Skype for Business Server Management Shell. Analogamente, l'unico modo per aggiungere, modificare o rimuovere i numeri di prelievo delle chiamate di gruppo consiste nell'usare Skype for Business Server Management Shell. 
  
Dopo aver configurato i numeri del gruppo di prelievo delle chiamate, è possibile assegnare gli utenti a un gruppo di prelievo delle chiamate. Tutti gli utenti a cui è assegnato un gruppo di prelievo di chiamata possono rispondere alle chiamate di altri utenti. Quando una chiamata viene rilasciata a un utente assegnato a un gruppo di prelievo di chiamata, qualsiasi altro utente che nota la chiamata può rispondere manualmente componendo il numero del gruppo di prelievo delle chiamate. L'utente che preleva la chiamata non deve necessariamente essere un membro del gruppo. Quando una chiamata viene rilevata da un altro utente, viene inviata una notifica al numero originariamente chiamato.
  
> [!NOTE]
> Un utente può essere membro di un solo gruppo di prelievo delle chiamate. 
  
> [!NOTE]
> Anche se qualsiasi utente nella distribuzione di Skype for Business Server può rispondere a una chiamata a un membro del gruppo di prelievo di chiamata, la persona che risponde alla chiamata deve conoscere il numero del gruppo di prelievo di chiamata corretto da comporre. 
  
Se un utente compone un numero di gruppo di prelievo di chiamata per rispondere a una chiamata quando si squillano più telefoni del gruppo, l'utente risponde alla chiamata che ha squillato più a lungo.
  
Le impostazioni di squillo simultaneo funzioneranno per gli utenti che dispongono del prelievo delle chiamate di gruppo. Vale a dire che una chiamata effettuata a un utente con prelievo di chiamata di gruppo suonerà per tutte le destinazioni configurate e un altro utente potrà rispondere alla chiamata. L'eccezione a questa regola è quella in cui l'utente configura lo squillo simultaneo per chiamare tutti i membri del team.
  
Non è possibile utilizzare il prelievo delle chiamate di gruppo per rispondere ai tipi di chiamate seguenti:
  
- Chiamate a una riga privata
    
- Chiamate da un contatto a cui è stata assegnata la relazione amici e familiari sulla privacy
    
    > [!TIP]
    > Un utente membro di un gruppo di prelievo di chiamata può impedire che determinate chiamate vengano recuperate tramite il ritiro delle chiamate di gruppo contrassegnando il contatto come contatto personale nel client Skype for business. Per contrassegnare un contatto come contatto personale, impostare la relazione di privacy per il contatto con gli amici e la famiglia. Qualsiasi chiamata in arrivo da contatti con la relazione di privacy impostata su amici e familiari non può essere recuperata tramite il prelievo delle chiamate di gruppo. 
  
- Parte video delle chiamate audio/video 
    
    > [!NOTE]
    > Se un utente risponde a una chiamata audio/video, l'utente riceverà solo l'audio. La chiamata di persona o la persona che risponde alla chiamata può inoltrare la richiesta di aggiunta di un video. 
  
- Chiamate di chiamata simultanee che vengono instradate ai membri delle chiamate del team
    
- Chiamate instradate a un delegato
    
- Chiamate instradate a un Response Group
    
I seguenti tipi di utenti non possono partecipare al ritiro delle chiamate di gruppo. Vale a dire che non devono essere inclusi in un gruppo di prelievo di chiamata di gruppo e non possono rispondere alle chiamate per gli utenti che dispongono del prelievo di chiamata di gruppo abilitato.
  
- Utenti ospitati online in una distribuzione ibrida
    
- Utenti che non sono ospitati in un pool di Skype for Business Server 2015 o in un pool di Lync Server 2013 con aggiornamenti cumulativi per Lync Server 2013: febbraio 2013 in una distribuzione locale
    
Se non si risponde a una chiamata a un membro di un gruppo di prelievo di chiamata, la chiamata viene instradata come specificato nelle impostazioni client. Vale a dire che la chiamata viene inviata alla segreteria telefonica o viene inoltrata a una destinazione diversa, come specificato nelle impostazioni del client.
  
## <a name="deployment-and-requirements"></a>Distribuzione e requisiti

Il prelievo delle chiamate di gruppo viene distribuito automaticamente quando si distribuisce VoIP aziendale e l'applicazione Parcheggio di chiamata. È possibile abilitare il ritiro delle chiamate di gruppo configurando la tabella orbit del parcheggio di chiamata con intervalli di numeri distinti designati come numeri del gruppo di prelievo di chiamata e quindi assegnando gli utenti ai gruppi di prelievo di chiamata e abilitando gli utenti al ritiro delle chiamate di gruppo.
  
## <a name="clients-supported-for-group-call-pickup"></a>Client supportati per il ritiro delle chiamate di gruppo

È possibile utilizzare uno dei seguenti client per rispondere alle chiamate ai membri di prelievo delle chiamate di gruppo:
  
- Skype for Business
    
- Lync 2013
    
- Lync 2010
    
- Lync Phone Edition
    
> [!NOTE]
> Gli utenti possono utilizzare uno di questi client per rispondere alle chiamate ai membri di prelievo delle chiamate di gruppo, ma gli utenti devono essere ospitati in un pool di server Skype for business o in un pool di Lync Server 2013 con aggiornamenti cumulativi per Lync Server 2013: febbraio 2013. 
  
I client e i dispositivi seguenti non sono supportati per la raccolta delle chiamate ai membri di prelievo delle chiamate di gruppo:
  
- Lync Mobile
    
- App Lync per Windows 8 e Windows RT
    
- Lync per iPad
    
- Telefoni analogici
    
- Telefoni con numeri PSTN (Public Switched Telephone Network)
    
## <a name="capacity-planning"></a>Pianificazione della capacità

Nella tabella seguente viene descritto il modello utente di prelievo delle chiamate di gruppo che è possibile utilizzare come base per i requisiti di pianificazione della capacità.
  
> [!IMPORTANT]
> Il prelievo delle chiamate di gruppo si basa sull'applicazione Parcheggio di chiamata. Tenere presente che, per la pianificazione della capacità di ripristino di emergenza, ogni pool di un pool associato dovrebbe essere in grado di gestire i carichi di lavoro per i servizi del parcheggio di chiamata, incluso il prelievo delle chiamate di gruppo, in entrambi i pool. 
  
**Modello utente di prelievo delle chiamate di gruppo**

|**Metrica**|**Per pool Front End  <br/>  (con 8 Front End Server)**|**Per server Standard Edition**|
|:-----|:-----|:-----|
|Numero consigliato di utenti per gruppo  <br/> |50  <br/> |50  <br/> |
|Numero consigliato di gruppi  <br/> |500  <br/> |60  <br/> |
|Numero massimo di utenti per pool abilitato per il prelievo delle chiamate di gruppo  <br/> |25.000  <br/> |3.000  <br/> |
|Velocità massima delle chiamate in arrivo per il numero totale di utenti abilitati per il prelievo delle chiamate di gruppo per pool al minuto  <br/> |500  <br/> |60  <br/> |
|Velocità massima delle chiamate recuperate dagli utenti con il prelievo di chiamata di gruppo per pool al minuto  <br/> |200  <br/> |25  <br/> |
   
> [!NOTE]
> Per i pool Front end con meno di otto Front End Server, calcolare le metriche linearmente. Ad esempio, se il pool Front End ha un front end server, calcolare il carico massimo come 1/8 dei valori riportati nella tabella. 
  
> [!NOTE]
> È possibile aumentare o diminuire il numero consigliato di utenti per gruppo e numero di gruppi finché non si supera il numero massimo di utenti per pool. Ad esempio, il server Standard Edition può avere 120 gruppi con 25 utenti per gruppo, perché il numero di utenti abilitati per il prelievo delle chiamate di gruppo è ancora all'interno del massimo modello utente (ovvero 120 gruppi per 25 utenti è 3.000 utenti abilitati per il ritiro delle chiamate di gruppo). 
  

