---
title: Teams caso di studio contoso vocale
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 06/17/2020
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
ms.reviewer: jowrig
search.appverid: MET150
f1.keywords:
- NOCSH
description: Teams caso di studio vocale per multinazionali
appliesto:
- Microsoft Teams
ms.openlocfilehash: f1ba92794b2ba17cc23e1bca55800c9307707636
ms.sourcegitcommit: af15d99837a389b6b26952211e65cd68c4b7f46e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/18/2020
ms.locfileid: "44786006"
---
# <a name="contoso-case-study-location-based-routing"></a>Case study contoso: Location-Based Routing

Location-Based Routing (LBR) è una funzionalità che limita il bypass a pedaggio in base ai criteri e alla posizione fisica dell'utente al momento dell'esecuzione o della ricezione di una chiamata.  

## <a name="overview"></a>Panoramica

Contoso ha due uffici in un paese in cui è illegale aggirare il provider PSTN (Public Switched Telephone Network) per ridurre i costi delle chiamate interurbane. L'ufficio principale ha una connessione Internet usata dall'ufficio principale e dal secondo ufficio. Ogni ufficio ha un proprio Session Border Controller (SBC) connesso a un gestore PSTN.  
 
In questo paese, Contoso aveva configurato LBR per la distribuzione Skype for Business distribuzione. Per determinare come configurare LBR per l'Teams, Contoso leggere Pianificare Location-Based [routing per il routing diretto](location-based-routing-plan.md). Contoso ha stabilito che Teams e Skype for Business seguono gli stessi scenari in cui è possibile effettuare una chiamata, quando può essere ricevuta, quando una chiamata PSTN può essere trasferita a un utente di Teams e quando è possibile trasferire un altro utente Teams alla chiamata PSTN.  

Per Skype for Business, LBR è stato configurato con il trunk SIP SBC (Session Border Controller) che si connette al gestore PSTN. Per questo SBC, Contoso [](direct-routing-border-controllers.md) ha esaminato l'elenco di SBC certificati e ha stabilito che la SBC distribuita è certificata per il routing diretto, ma non è certificata per Media Bypass. Per supportare LBR, il routing diretto deve essere configurato sul sito SBC, deve esserci un'uscita Internet locale e SBC deve essere configurato per Media Bypass. In base a queste informazioni, Contoso ha deciso quanto segue:

- Per ritardare l'abilitazione Teams LBR fino a quando l'SBC esistente non è certificato per Media Bypass.   

- Contoso ha deciso di usare il sito principale SBC per la route diretta a Office 365.  Il sito principale SBC sarà il proxy SBC per il sito remoto.  

- Contoso ha usato un consulente di terze parti con sede in India per fornire assistenza nella certificazione della configurazione LBR con la società di telefonia nel paese.  

- Per supportare gli utenti che lavorano dall'esterno dell'ufficio a effettuare chiamate PSTN, l'azienda ha emesso un telefono cellulare ai propri dipendenti. 

I diagrammi seguenti illustrano le distribuzioni prima e dopo per un paese con normative di telefonia che richiedono Location-Based routing:

**Distribuzione originale**

![Diagramma che mostra prima dello stato](media/voice-case-study-5.png)

**Distribuzione con routing diretto**

![Diagramma che mostra prima dello stato](media/voice-case-study-6.png)


## <a name="configuration"></a>Configurazione: 

Per configurare i componenti di rete in Teams, Contoso ha seguito le istruzioni in Gestire la topologia di rete [per le funzionalità vocali cloud.](manage-your-network-topology.md) Contoso ha completato i passaggi seguenti per configurare Location-Based routing: 

- Definire le aree di rete: è stata definita un'area di rete. 

- Definire i siti di rete: sono stati definiti due siti di rete. Un sito per ogni sede dell'area geografica.

- Definire subnet di rete: ogni piano all'interno di un ufficio ha una propria subnet per la rete cablata e wireless. Questa configurazione ha restituito 20 subnet per Contoso. 

- Definisci indirizzi IP attendibili: gli indirizzi IP esterni per SBC sono stati aggiunti all'indirizzo IP attendibile.  

