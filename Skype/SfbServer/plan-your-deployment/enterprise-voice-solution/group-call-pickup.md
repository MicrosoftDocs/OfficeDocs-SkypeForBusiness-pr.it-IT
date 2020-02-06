---
title: Pianificare il ritiro delle chiamate di gruppo in Skype for business
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
ms.openlocfilehash: 0be7adb5b3832851b9c38179416cfedb414508b0
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41802876"
---
# <a name="plan-for-group-call-pickup-in-skype-for-business"></a>Pianificare il ritiro delle chiamate di gruppo in Skype for business
 
Pianificazione del ritiro delle chiamate di gruppo in Skype for Business Server VoIP aziendale, che consente agli utenti di rispondere alle chiamate originariamente destinate ad altri.
  
Il pick-up delle chiamate di gruppo consente agli utenti di rispondere alle chiamate in arrivo ai loro colleghi tramite telefoni. In questo modo si aumenta la disponibilità della linea di un utente, consentendo ad altri utenti di rispondere a una chiamata in arrivo componendo un numero di gruppo di pick-up chiamata. Quando viene distribuito il prelievo delle chiamate di gruppo, il numero di chiamate in arrivo indirizzate alla segreteria telefonica può essere notevolmente ridotto, particolarmente utile per le chiamate provenienti da clienti esterni all'organizzazione.
  
La caratteristica raccolta chiamate di gruppo è stata progettata in particolare per le unità aziendali in ambienti Office aperti. Le chiamate in arrivo non sono di disturbo perché squillano solo nella destinazione prevista. Tuttavia, gli altri utenti che sentono l'anello possono comunque prendere la chiamata semplicemente componendo il numero di gruppo. 
  
In ambienti in cui gli utenti non si trovano in un layout Office aperto o in cui gli utenti che condividono una responsabilità comune sono distribuiti geograficamente, la chiamata del team presenta la soluzione più appropriata. La differenza principale tra il pick-up delle chiamate di gruppo e la chiamata del team consiste nel fatto che, con il ritiro delle chiamate di gruppo, una chiamata in arrivo viene squillata solo nella destinazione desiderata, ma chiunque può comunque scegliere di rispondere chiamando un numero di gruppo. Con la chiamata del team, la chiamata squilla in tutti i telefoni dei membri del team e qualsiasi utente del team può prendere il telefono per rispondere alla chiamata. Un'ulteriore differenza tra il ritiro delle chiamate di gruppo e la chiamata del team consiste nel fatto che il ritiro delle chiamate di gruppo è gestito da un amministratore tramite Skype for Business Server. Con la chiamata del team, gli utenti finali gestiscono la funzionalità usando il client Skype for business. Con il pick-up delle chiamate di gruppo, quindi, questo aspetto della gestione delle chiamate può essere centralizzato.
  
Il ritiro delle chiamate di gruppo viene compilato nell'applicazione Call Park. Quando si distribuisce il pickup di una chiamata di gruppo, è possibile configurare la tabella Orbit di Call Park con intervalli distinti di numeri di interno designati come numeri di gruppo di pick-up delle chiamate. Come i numeri delle orbite di Call Park, i numeri dei gruppi di pickup delle chiamate devono essere estensioni virtuali che non hanno un utente o un telefono assegnato. Ogni pool Front end in cui si distribuisce il pickup di una chiamata di gruppo può avere uno o più intervalli di numeri di gruppo di prelievo chiamate. Gli intervalli di numeri di gruppo devono essere univoci a livello globale in tutta la distribuzione di Skype for Business Server. 
  
> [!NOTE]
> Gli intervalli di numeri designati come numeri di prelievo delle chiamate di gruppo nella tabella Orbit di parcheggio delle chiamate non possono essere gestiti o visualizzati usando il pannello di controllo di Skype for Business Server. L'unico modo per visualizzare tutti gli intervalli di numeri nella tabella Orbit di Call Park consiste nell'usare Skype for Business Server Management Shell. Analogamente, l'unico modo per aggiungere, modificare o rimuovere i numeri di prelievo delle chiamate di gruppo consiste nell'usare Skype for Business Server Management Shell. 
  
Dopo aver configurato i numeri dei gruppi di raccolta chiamate, assegnare gli utenti a un gruppo di raccolta chiamate. Qualsiasi utente assegnato a un gruppo di raccolta chiamate può rispondere alle chiamate di altri utenti. Quando una chiamata viene fornita a un utente assegnato a un gruppo di raccolta chiamate, qualsiasi altro utente che nota la chiamata può rispondere manualmente chiamando il numero del gruppo di raccolta chiamate. L'utente che preleva la chiamata non deve necessariamente essere un membro del gruppo. Quando una chiamata viene rilevata da un altro utente, viene inviata una notifica al numero originariamente chiamato.
  
> [!NOTE]
> Un utente può essere un membro di un solo gruppo di raccolta chiamate. 
  
> [!NOTE]
> Anche se qualsiasi utente della distribuzione di Skype for Business Server può rispondere a una chiamata a un membro del gruppo di prelievo delle chiamate, la persona che risponde alla chiamata deve conoscere il numero del gruppo di pick-up chiamata corretto. 
  
Se un utente compone un numero di gruppo di pick-up chiamata per rispondere a una chiamata quando si squillano più telefoni nel gruppo, l'utente risponde alla chiamata che ha squillato il più a lungo.
  
Le impostazioni di chiamata simultanee funzionano per gli utenti che hanno un pick-up delle chiamate di gruppo. Vale a dire che una chiamata effettuata a un utente che ha un pickup per la chiamata di gruppo suonerà per tutte le destinazioni configurate e un altro utente può rispondere alla chiamata. L'eccezione a questa regola è quando l'utente configura lo squillo simultaneo per chiamare tutti i membri del team.
  
Non è possibile usare il pick-up per rispondere ai tipi di chiamata seguenti:
  
- Chiamate a una riga privata
    
- Chiamate di un contatto a cui sono stati assegnati gli amici e la relazione di privacy della famiglia
    
    > [!TIP]
    > Un utente che fa parte di un gruppo di raccolta chiamate può impedire che determinate chiamate vengano recuperate tramite il ritiro delle chiamate di gruppo contrassegnando il contatto come contatto personale nel client Skype for business. Per contrassegnare un contatto come contatto personale, impostare la relazione di privacy per il contatto con amici e familiari. Qualsiasi chiamata in arrivo da contatti con la relazione di privacy impostata su amici e familiari non può essere recuperata tramite raccolta chiamate di gruppo. 
  
- Parte video delle chiamate audio/video 
    
    > [!NOTE]
    > Se un utente risponde a una chiamata audio/video, l'utente riceve solo l'audio. La chiamata di persona o la persona che risponde alla chiamata può escalation per l'aggiunta di un video. 
  
- Chiamate di chiamata simultanee instradate ai membri delle chiamate del team
    
- Chiamate instradate a un delegato
    
- Chiamate instradate a un gruppo di risposte
    
I tipi di utenti seguenti non possono partecipare al ritiro delle chiamate di gruppo. Vale a dire che non devono essere inclusi in un gruppo di raccolta chiamate di gruppo e non possono raccogliere le chiamate per gli utenti che hanno abilitato il pick-up delle chiamate di gruppo.
  
- Utenti residenti online in una distribuzione ibrida
    
- Utenti non residenti in un pool di Skype for Business Server 2015 o in un pool di Lync Server 2013 con aggiornamenti cumulativi per Lync Server 2013: febbraio 2013 in una distribuzione locale
    
Se non si risponde a una chiamata a un membro di un gruppo di raccolta chiamate, la chiamata viene instradata come specificato nelle impostazioni del client. Vale a dire che la chiamata passa alla segreteria telefonica o viene inoltrata a una destinazione diversa, come specificato nelle impostazioni del client.
  
## <a name="deployment-and-requirements"></a>Distribuzione e requisiti

Il ritiro delle chiamate di gruppo viene distribuito automaticamente quando si distribuisce VoIP aziendale e l'applicazione Call Park. Puoi abilitare il ritiro delle chiamate di gruppo configurando la tabella Orbit di Call Park con intervalli distinti di numeri designati come numeri di gruppo di prelievo chiamate e quindi assegnando gli utenti per chiamare i gruppi di prelievo e abilitare gli utenti per il ritiro delle chiamate di gruppo.
  
## <a name="clients-supported-for-group-call-pickup"></a>Client supportati per il ritiro delle chiamate di gruppo

Uno dei client seguenti può essere usato per rispondere alle chiamate ai membri del pick-up delle chiamate di gruppo:
  
- Skype for business
    
- Lync 2013
    
- Lync 2010
    
- Lync Phone Edition
    
> [!NOTE]
> Gli utenti possono usare uno di questi client per rispondere alle chiamate ai membri del pick-up delle chiamate di gruppo, ma gli utenti devono essere ospitati in un pool di Skype for Business Server o in un pool di Lync Server 2013 con aggiornamenti cumulativi per Lync Server 2013: febbraio 2013. 
  
I client e i dispositivi seguenti non sono supportati per raccogliere le chiamate ai membri del pick-up delle chiamate di gruppo:
  
- Lync mobile
    
- App Lync per Windows 8 e Windows RT
    
- Lync per iPad
    
- Telefoni analogici
    
- Telefoni con numeri PSTN (Public Switched Telephone Network)
    
## <a name="capacity-planning"></a>Pianificazione della capacità

La tabella seguente descrive il modello di utente di prelievo delle chiamate di gruppo che puoi usare come base per i requisiti di pianificazione della capacità.
  
> [!IMPORTANT]
> Il ritiro delle chiamate di gruppo si basa sull'applicazione Call Park. Tieni presente che, per la pianificazione della capacità di ripristino di emergenza, ogni pool di un pool associato dovrebbe essere in grado di gestire i carichi di lavoro per i servizi di Call Park, incluso il ritiro delle chiamate di gruppo, in entrambi i pool. 
  
**Modello utente di raccolta chiamate di gruppo**

|**Metrica**|**Per pool <br/> front-end (con 8 server front-end)**|**Per server Standard Edition**|
|:-----|:-----|:-----|
|Numero di utenti consigliati per gruppo  <br/> |50  <br/> |50  <br/> |
|Numero consigliato di gruppi  <br/> |500  <br/> |60  <br/> |
|Numero massimo di utenti per pool abilitato per il ritiro delle chiamate di gruppo  <br/> |25.000  <br/> |3.000  <br/> |
|Tasso massimo delle chiamate in arrivo per il totale degli utenti abilitati per il ritiro delle chiamate di gruppo per pool al minuto  <br/> |500  <br/> |60  <br/> |
|Tasso massimo delle chiamate recuperate dagli utenti con il ritiro delle chiamate di gruppo per pool al minuto  <br/> |200  <br/> |25  <br/> |
   
> [!NOTE]
> Per i pool Front-end con meno di otto server front-end, calcolare le metriche linearmente. Ad esempio, se il pool Front-End ha un server front-end, calcolare il carico massimo come 1/8 dei valori visualizzati nella tabella. 
  
> [!NOTE]
> È possibile aumentare o ridurre il numero di utenti consigliati per ogni gruppo e numero di gruppi purché non venga superato il numero massimo di utenti per pool. Ad esempio, il server Standard Edition può avere gruppi di 120 con 25 utenti per gruppo, perché il numero di utenti abilitati per il ritiro delle chiamate di gruppo è ancora all'interno del massimo del modello utente (ovvero 120 gruppi per 25 utenti è consentito agli utenti di 3.000 per il ritiro delle chiamate di gruppo). 
  

