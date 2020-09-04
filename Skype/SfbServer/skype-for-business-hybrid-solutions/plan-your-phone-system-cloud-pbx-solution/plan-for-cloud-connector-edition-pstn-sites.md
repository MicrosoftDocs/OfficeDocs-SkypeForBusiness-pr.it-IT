---
title: Pianificare i siti PSTN Cloud Connector Edition
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/30/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: cec2d9bf-2deb-482c-841b-0e3599f94b50
description: Leggere questo argomento per informazioni su come pianificare i siti PSTN di Cloud Connector Edition per garantire un routing efficace e redditizio delle chiamate.
ms.openlocfilehash: 3b4320e12a87c771e28fce445102327c7783a5d2
ms.sourcegitcommit: b424ab14683ab5080ebfd085adff7c0dbe1be84c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/03/2020
ms.locfileid: "47358802"
---
# <a name="plan-for-cloud-connector-edition-pstn-sites"></a>Pianificare i siti PSTN Cloud Connector Edition

> [!Important]
> Cloud Connector Edition si ritirerà il 31 luglio 2021 insieme a Skype for business online. Dopo che l'organizzazione ha eseguito l'aggiornamento ai team, informazioni su come connettere la rete di telefonia locale ai team che utilizzano il [routing diretto](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page).
 
Leggere questo argomento per informazioni su come pianificare i siti PSTN di Cloud Connector Edition per garantire un routing efficace e redditizio delle chiamate.
  
In questo argomento viene descritto cosa è necessario sapere su cloud Connector Edition e routing delle chiamate in modo che sia possibile pianificare i siti PSTN del connettore Cloud. Un sito PSTN è una combinazione di dispositivi di connettori cloud, distribuiti nello stesso percorso e con gateway PSTN comuni ad essi connessi. In questo argomento viene illustrato come configurare la topologia del sito del connettore Cloud per garantire che i siti dei connettori cloud possano gestire il routing in ingresso e in uscita per tutti gli utenti assegnati a un sito nel modo più efficiente e conveniente possibile. Per ulteriori informazioni su cloud Connector e sui vantaggi dei siti PSTN, leggere [Plan for Skype for Business Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md). 
  
## <a name="cloud-connector-pstn-sites-and-call-routing"></a>Siti PSTN del connettore Cloud e routing delle chiamate

I siti PSTN dei connettori cloud sono un costrutto di topologia creato per impedire inutili tariffe interurbane e tra paesi e per garantire che le chiamate di emergenza in uscita vengano instradate al trunk appropriato. Per garantire un routing efficiente e redditizio delle chiamate, incluse le chiamate ai servizi di emergenza, è necessario pianificare attentamente i siti PSTN e in che modo gli utenti vengono assegnati a ogni sito. 
  
Nell'ambito della pianificazione del connettore Cloud, è essenziale parlare con i vettori sul luogo in cui si trovano gli uffici e gli utenti e in cui i trunk PSTN terminano dal gestore. È necessario collaborare con i vettori per determinare in che modo è possibile instradare le chiamate di emergenza e quindi utilizzare tali informazioni per definire i siti PSTN dei connettori cloud e assegnare gli utenti ai siti corretti. Ad esempio, è necessario assicurarsi che i trunk che terminano in un centro dati in cui il sito PSTN sia allungato siano configurati per gestire il routing in ingresso e in uscita per tutti i numeri assegnati agli utenti del sito. 
  
Ogni accessorio Cloud Connector può essere connesso a diversi gateway IP, IP PBX o Session Border Controller (SBCs). Poiché i gateway e i sistemi PBX sono connessi ai trunk Telco (Trunks PRI o SIP), gli apparecchi dei connettori cloud sono connessi logicamente ai trunk PSTN per le chiamate in ingresso e in uscita. Con il connettore Cloud e la connettività PSTN locale, è possibile ottenere il trunk e i numeri di telefono associati dal provider di servizi locali. Se la propria azienda è un'azienda di grandi dimensioni, è possibile che si disponga di più vettori, soprattutto se la propria azienda si estende su più di una città, uno stato o un paese. Dal momento che il vettore è proprietario del numero di telefono, il corriere è responsabile della gestione delle chiamate di emergenza.
  
Skype for business online tratta equamente tutti gli apparecchi dei connettori cloud in un sito e instraderà le chiamate in uscita su una base rotante a dispositivi cloud Connector nello stesso sito. Ogni connettore Cloud in un sito è connesso alla rete con lo stesso set di trunk PSTN (completamente incassato). Poiché ogni utente è associato a un sito PSTN del connettore Cloud, qualsiasi chiamata in uscita da tale utente (normale o emergenza) verrà assegnata a uno degli apparecchi del connettore Cloud nel sito PSTN a cui è associato l'utente. 
  
Il connettore cloud esegue il routing delle chiamate statiche ai propri gateway IP, IP-PBX, SBCs o trunk PSTN diretti. Il connettore Cloud non è ancora in grado di eseguire il routing dinamico verso un trunk in base alla destinazione (per il routing dei costi minimi) o in base all'origine (chiamate di emergenza statiche o dinamiche). Le chiamate in ingresso non sono un problema poiché la chiamata può provenire solo da un trunk associato al numero. Le chiamate in uscita, tuttavia, possono accedere a qualsiasi accessorio Cloud Connector in un sito (e per estensione i trunk PSTN associati a quell'accessorio Cloud Connector) che può causare chiamate interurbane indesiderate. Inoltre, le chiamate di emergenza non passeranno se il sito PSTN del connettore Cloud viene esteso nei data center con diversi codici di area o vettori.
  
## <a name="an-example"></a>Un esempio

Nell'esempio seguente viene illustrato come raggruppare i trunk per i siti PSTN e come assegnare gli utenti ai siti. Per Contoso Company, si presuppone quanto segue:
  
- Sono disponibili quattro utenti: 
    
  - Utente a in Redmond WA (Stati Uniti)
    
  - Utente B in Bellevue WA (Stati Uniti)
    
  - Utente C in Centralia WA (Stati Uniti)
    
  - Utente D in Portland o (USA)
    
- Carrier A fornisce numeri di telefono e trunk in:
    
  - Redmond (prefisso 425)
    
  - Bellevue (prefisso indicativo 425)
    
  - Centralia (prefisso 360)
    
- Carrier B fornisce numeri di telefono e trunk in:
    
  -  Portland (prefisso indicativo 503)
    
Dato che l'utente a di Redmond (Data Center A) e l'utente B in Bellevue (Data Center B) sono in periferia uno accanto all'altro e nello stesso indicativo di località (425), il Carrier A dovrebbe essere in grado di effettuare una chiamata di emergenza dall'utente A a Redmond sul tronco di Bellevue. 
  
Di conseguenza, gli utenti A e B e i trunk del connettore Cloud per Bellevue e Redmond possono essere nello stesso sito PSTN del connettore Cloud, come illustrato nel diagramma seguente. Le chiamate di emergenza degli utenti in un ufficio possono essere instradate ai trunk nell'altro. Tuttavia, è necessario verificare con il gestore che funzionerà.
  
![Come configurare i siti PSTN](../../media/2659caa7-9c18-4d4f-9c7a-61d0e6a07dc3.png)
  
Tenere presenti anche gli esempi seguenti:
  
- L'utente C in Centralia, il cui numero è fornito dal vettore A, è a due ore di distanza e in un altro prefisso (360), da altri vettori a utenti del codice di area Bellevue e Redmond 425. 
    
    Pertanto, anche se una chiamata proviene dal Carrier A, è possibile che il software di routing delle chiamate del vettore in Centralia area code 360 possa rifiutare una chiamata di emergenza in ingresso proveniente dall'utente B del codice di area Bellevue 425. In questo caso, è importante che il vettore confermi che il connettore Cloud e i trunk associati nei siti PSTN di Centralia possano gestire le chiamate tra distanze e codici di area.
    
- L'utente D in Portland utilizza un numero e un trunk forniti dal Carrier B, quindi è estremamente improbabile che il Carrier B esegua una chiamata di emergenza da un numero di telefono di proprietà di un operatore A. Pertanto, l'utente D e l'accessorio Cloud Connector e trunk associati a Portland dovranno trovarsi in un altro sito PSTN.
    

