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
ms.localizationpriority: medium
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: cec2d9bf-2deb-482c-841b-0e3599f94b50
description: Leggere questo argomento per informazioni su come pianificare i siti PSTN di Cloud Connector Edition per garantire un routing delle chiamate efficiente ed economicamente conveniente.
ms.openlocfilehash: 50b30a5071dd14cc0016419d85406b7c50d85387
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/30/2021
ms.locfileid: "58729235"
---
# <a name="plan-for-cloud-connector-edition-pstn-sites"></a>Pianificare i siti PSTN Cloud Connector Edition

> [!Important]
> Cloud Connector Edition andrà in pensione il 31 luglio 2021 insieme a Skype for Business Online. Dopo l'aggiornamento dell'organizzazione a Teams, informazioni su come connettere la rete di telefonia locale a Teams tramite [Routing diretto](/MicrosoftTeams/direct-routing-landing-page).
 
Leggere questo argomento per informazioni su come pianificare i siti PSTN di Cloud Connector Edition per garantire un routing delle chiamate efficiente ed economicamente conveniente.
  
In questo argomento vengono descritte le informazioni necessarie su Cloud Connector Edition e il routing delle chiamate in modo da poter pianificare i siti PSTN del connettore cloud. Un sito PSTN è una combinazione di appliance Cloud Connector, distribuite nella stessa posizione e con gateway PSTN comuni connessi. In questo argomento viene illustrato come configurare la topologia del sito Cloud Connector per garantire che i siti Cloud Connector siano in grado di gestire il routing sia in ingresso che in uscita per tutti gli utenti assegnati a un sito nel modo più conveniente ed efficace possibile. Per ulteriori informazioni su Cloud Connector e sui vantaggi dei siti PSTN, vedere [Plan for Skype for Business Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md). 
  
## <a name="cloud-connector-pstn-sites-and-call-routing"></a>Siti PSTN del connettore cloud e routing delle chiamate

I siti PSTN del connettore cloud sono un costrutto di topologia creato per evitare inutili tariffe interurbane e interurbane e per garantire che le chiamate di emergenza in uscita siano instradati al trunk appropriato. Per garantire un routing efficiente ed efficiente delle chiamate, incluse le chiamate ai servizi di emergenza, è necessario pianificare attentamente i siti PSTN e il modo in cui gli utenti vengono assegnati a ogni sito. 
  
Nell'ambito della pianificazione di Cloud Connector, è essenziale parlare con gli operatori della posizione degli uffici e degli utenti e del punto in cui i trunk PSTN terminano dal gestore. È necessario collaborare con gli operatori per determinare come instradare le chiamate di emergenza e quindi utilizzare queste informazioni per definire i siti PSTN di Cloud Connector e assegnare gli utenti ai siti appropriati. Ad esempio, è necessario verificare che i trunk che terminano in un datacenter in cui il sito PSTN è allungato siano configurati per gestire il routing sia in ingresso che in uscita per tutti i numeri assegnati agli utenti del sito. 
  
Ogni appliance Cloud Connector può essere connessa a diversi gateway IP, IP-IP-IP o Session Border Controller (SBC). Poiché i gateway e i dispositivi PBX sono connessi a trunk telco (trunk PRI o SIP), le appliance cloud Connector sono connesse logicamente ai trunk PSTN per le chiamate in ingresso e in uscita. Con Cloud Connector e la connettività PSTN locale, ottieni il trunk e i numeri di telefono associati dall'operatore locale. Se la tua azienda è un'azienda di grandi dimensioni, potresti avere più di un operatore, soprattutto se l'azienda si estende su più città, stati o paesi. Poiché l'operatore è proprietario del numero di telefono, è responsabile della gestione delle chiamate di emergenza.
  
Skype for Business Online tratta equamente tutte le appliance Cloud Connector in un sito e instraderà le chiamate in uscita a rotazione alle appliance Cloud Connector nello stesso sito. Ogni connettore cloud in un sito è connesso allo stesso set di trunk PSTN (completamente mesh). Poiché ogni utente è associato a un sito PSTN del connettore cloud, qualsiasi chiamata in uscita da tale utente (normale o di emergenza) verrà assegnata a una delle appliance Cloud Connector nel sito PSTN a cui è associato l'utente. 
  
Cloud Connector esegue il routing delle chiamate statiche ai relativi gateway IP collegati, IP-IP, SBC o trunk PSTN diretti. Cloud Connector non è ancora in grado di instradamento dinamico a un trunk in base alla destinazione (per il routing meno costo) o in base all'origine (chiamate di emergenza statiche o dinamiche). Le chiamate in ingresso non sono un problema, poiché la chiamata può derivare solo da un trunk associato al numero. Le chiamate in uscita, tuttavia, possono passare a qualsiasi appliance Cloud Connector in un sito (e per estensione i trunk PSTN collegati a tale appliance Cloud Connector) che possono causare chiamate interurbane indesiderate. Inoltre, le chiamate di emergenza non verranno effettuate se il sito PSTN del connettore cloud è disteso tra datacenter con codici di area o vettori diversi.
  
## <a name="an-example"></a>Un esempio

Nell'esempio seguente viene illustrato come raggruppare i trunk nei siti PSTN e come assegnare utenti ai siti. Per la società Contoso, presupporre quanto segue:
  
- Sono disponibili quattro utenti: 
    
  - Utente A in Redmond WA (USA)
    
  - Utente B in Bellevue WA (USA)
    
  - Utente C in Centralia WA (USA)
    
  - Utente D in Portland OR (USA)
    
- Carrier A fornisce numeri di telefono e trunk in:
    
  - Redmond (codice area 425)
    
  - Bellevue (codice area 425)
    
  - Centralia (codice area 360)
    
- Carrier B fornisce numeri di telefono e trunk in:
    
  -  Portland (codice area 503)
    
Poiché l'utente A in Redmond (Data Center A) e l'utente B in Bellevue (Data Center B) sono in sobborghi uno accanto all'altro e nello stesso codice area (425), carrier A dovrebbe essere in grado di eseguire una chiamata di emergenza dall'utente A a Redmond sul trunk in Bellevue. 
  
Di conseguenza, gli utenti A e B e i trunk del connettore cloud per Bellevue e Redmond, possono probabilmente essere nello stesso sito PSTN del connettore cloud, come illustrato nel diagramma seguente. Le chiamate di emergenza degli utenti di un ufficio possono essere instradati ai trunk nell'altra. Tuttavia, dovresti verificare con il tuo operatore che questo funzionerà.
  
![Come configurare i siti PSTN.](../../media/2659caa7-9c18-4d4f-9c7a-61d0e6a07dc3.png)
  
Considerare anche gli esempi seguenti:
  
- L'utente C in Centralia, il cui numero è fornito dal vettore A, è a due ore di auto e in un codice di area diverso (360), da altri utenti carrier A nel codice di area Bellevue e Redmond 425. 
    
    Pertanto, anche se una chiamata proviene dal vettore A, è possibile che il software di instradamento delle chiamate dell'operatore nel codice di area Centralia 360 possa rifiutare una chiamata di emergenza in arrivo proveniente dall'utente B nel codice di area Bellevue 425. In questo caso è fondamentale che l'operatore confermi che Cloud Connector e i trunk associati nei siti CENTRALIA PSTN possano gestire le chiamate tra distanze e codici di area.
    
- L'utente D di Portland usa un numero e un trunk forniti dal vettore B, quindi è altamente improbabile che il vettore B possa eseguire una chiamata di emergenza da un numero di telefono di proprietà del vettore A. L'utente D e l'appliance Cloud Connector e i trunk associati a Portland devono pertanto trovarsi in un sito PSTN diverso.
