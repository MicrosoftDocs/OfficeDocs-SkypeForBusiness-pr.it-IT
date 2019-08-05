---
title: Pianificare i siti PSTN di Cloud Connector Edition
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/30/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: cec2d9bf-2deb-482c-841b-0e3599f94b50
description: Leggere questo argomento per informazioni su come pianificare i siti PSTN di Cloud Connector Edition per garantire un routing efficace ed efficiente delle chiamate.
ms.openlocfilehash: 7afc5ac09e80edf6b1502e9d169aee77b3bd69b6
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36190724"
---
# <a name="plan-for-cloud-connector-edition-pstn-sites"></a>Pianificare i siti PSTN di Cloud Connector Edition
 
Leggere questo argomento per informazioni su come pianificare i siti PSTN di Cloud Connector Edition per garantire un routing efficace ed efficiente delle chiamate.
  
Questo argomento descrive le informazioni utili su cloud Connector Edition e su routing delle chiamate, in modo da poter pianificare i siti PSTN del connettore Cloud. Un sito PSTN è una combinazione di appliance di connettori cloud, distribuiti nella stessa posizione e con gateway PSTN comuni connessi. Questo argomento illustra come configurare la topologia del sito del connettore Cloud per verificare che i siti del connettore Cloud siano in grado di gestire il routing sia in ingresso che in uscita per tutti gli utenti assegnati a un sito nel modo più efficiente e conveniente possibile. Per altre informazioni su cloud Connector e sui vantaggi dei siti PSTN, leggere [piano per Skype for Business Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md). 
  
## <a name="cloud-connector-pstn-sites-and-call-routing"></a>Siti PSTN del connettore Cloud e routing delle chiamate

I siti PSTN per i connettori cloud sono un costrutto di topologia creato per evitare inutili tariffe interurbane e Inter-paese e per garantire che le chiamate di emergenza in uscita vengano instradate al trunk appropriato. Per garantire un routing efficace ed efficiente dei costi delle chiamate, incluse le chiamate ai servizi di emergenza, è necessario pianificare attentamente i siti PSTN e il modo in cui gli utenti vengono assegnati a ogni sito. 
  
Come parte della pianificazione per il connettore Cloud, è essenziale comunicare ai vettori la posizione in cui si trovano gli uffici e gli utenti e dove i trunk PSTN terminano dal vettore. È necessario collaborare con i vettori per determinare il modo in cui le chiamate di emergenza possono essere instradate e quindi usare queste informazioni per definire i siti PSTN del connettore Cloud e assegnare gli utenti ai siti appropriati. Ad esempio, devi assicurarti che i trunk che terminano in un centro dati in cui il sito PSTN sia allungato siano configurati per gestire il routing sia in ingresso che in uscita per tutti i numeri assegnati agli utenti di quel sito. 
  
Ogni accessorio Cloud Connector può essere connesso a diversi gateway IP, IP PBX o Session Border Controller (SBCs). Poiché i gateway e i PBX sono connessi a Trunks Telco (PRI o SIP Trunks), gli appliance di connessione cloud sono collegati logicamente ai trunk PSTN per le chiamate in ingresso e in uscita. Con il connettore Cloud e la connettività PSTN locale, è possibile ottenere il trunk e i numeri di telefono associati dal proprio gestore. Se la tua azienda è una società di grandi dimensioni, potresti avere più vettori, soprattutto se la tua azienda si estende su più di una città, uno stato o un paese. Dato che il gestore è proprietario del numero di telefono, il gestore è responsabile della gestione delle chiamate di emergenza.
  
Skype for business online tratta equamente tutti gli elettrodomestici di Cloud Connector in un sito e instraderà le chiamate in uscita su una base rotante per gli apparecchi di connessione cloud nello stesso sito. Ogni connettore Cloud in un sito è connesso alla stessa serie di trunk PSTN (completamente meshed). Poiché ogni utente è associato a un sito PSTN di Connector cloud, qualsiasi chiamata in uscita da tale utente (normale o emergenza) verrà assegnata a uno degli apparecchi di connessione cloud nel sito PSTN a cui l'utente è associato. 
  
Cloud Connector esegue il routing delle chiamate statiche ai gateway IP allegati, agli IP-PBX, ai trunk SBCs o Direct PSTN. Cloud Connector non è ancora in grado di eseguire il routing dinamico a un trunk basato sulla destinazione (per il routing meno costo) o sulla base dell'origine (chiamate di emergenza statiche o dinamiche). Le chiamate in ingresso non sono un problema perché la chiamata può provenire solo da un trunk associato al numero. Le chiamate in uscita, tuttavia, possono andare a qualsiasi appliance di connessione cloud in un sito (e per estensione i trunk PSTN collegati all'accessorio Cloud Connector) che può causare chiamate interurbane indesiderate. Inoltre, le chiamate di emergenza non verranno superate se il sito PSTN del connettore Cloud viene esteso tra i centri dati con codici di area o vettori diversi.
  
## <a name="an-example"></a>Esempio

L'esempio seguente mostra come raggruppare i trunk in siti PSTN e come assegnare utenti ai siti. Per Contoso Company, assumere quanto segue:
  
- Sono disponibili quattro utenti: 
    
  - Utente a in Redmond WA (Stati Uniti)
    
  - Utente B in Bellevue WA (Stati Uniti)
    
  - Utente C in Centralia WA (Stati Uniti)
    
  - Utente D in Portland o (USA)
    
- Il gestore A fornisce i numeri di telefono e i trunk in:
    
  - Redmond (prefisso 425)
    
  - Bellevue (prefisso 425)
    
  - Centralia (prefisso 360)
    
- Il vettore B fornisce i numeri di telefono e i trunk in:
    
  -  Portland (prefisso 503)
    
Poiché l'utente a in Redmond (centro dati A) e l'utente B in Bellevue (centro dati B) si trovano in periferia uno accanto all'altro e nello stesso prefisso (425), il vettore A dovrebbe essere in grado di eseguire una chiamata di emergenza dall'utente A a Redmond sul tronco di Bellevue. 
  
Di conseguenza, gli utenti A e B e i trunk dei connettori cloud per Bellevue e Redmond possono essere probabilmente nello stesso sito PSTN di Connector cloud, come illustrato nel diagramma seguente. Le chiamate di emergenza provenienti da utenti di un ufficio possono essere instradate a Trunks nell'altra. Tuttavia, è necessario verificare con il gestore che il problema funzionerà.
  
![Come configurare i siti PSTN](../../media/2659caa7-9c18-4d4f-9c7a-61d0e6a07dc3.png)
  
Consideriamo anche gli esempi seguenti:
  
- L'utente C in Centralia, il cui numero viene fornito dal vettore A, è a due ore di distanza, e in un altro prefisso (360), da altri vettori a utenti nel codice di area di Bellevue e Redmond 425. 
    
    Di conseguenza, anche se viene ricevuta una chiamata dal vettore A, è possibile che il software di routing delle chiamate del gestore in Centralia area code 360 possa rifiutare una chiamata di emergenza in arrivo proveniente dall'utente B nel codice dell'area Bellevue 425. In questo caso, è importante che il vettore confermi che il connettore Cloud e i trunk associati nei siti PSTN di Centralia possano gestire le chiamate tra le distanze e i codici di area.
    
- L'utente D in Portland USA un numero e un trunk forniti dal vettore B, quindi è altamente improbabile che il vettore B effettui una chiamata di emergenza da un numero di telefono di proprietà del vettore A. In modo che l'utente D e l'accessorio Cloud Connector e i trunk associati a Portland debbano essere ubicati in un sito PSTN diverso.
    

