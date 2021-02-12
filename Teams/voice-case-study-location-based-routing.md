---
title: Case study su Teams per Contoso
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
description: Case study vocale di Teams per multi-national corporation
appliesto:
- Microsoft Teams
ms.openlocfilehash: f1ba92794b2ba17cc23e1bca55800c9307707636
ms.sourcegitcommit: af15d99837a389b6b26952211e65cd68c4b7f46e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/18/2020
ms.locfileid: "44786006"
---
# <a name="contoso-case-study-location-based-routing"></a>Case study Contoso: Location-Based distribuzione

Location-Based Routing a pedaggio (LBR) è una funzionalità che limita il bypass a pedaggio in base ai criteri e alla posizione fisica dell'utente al momento dell'esecuzione o della ricezione di una chiamata.  

## <a name="overview"></a>Panoramica

Contoso ha due uffici in un paese in cui non è valido bypassare il provider PSTN (Public Switched Telephone Network) per ridurre i costi per le chiamate a distanza. L'ufficio principale ha una connessione Internet usata dall'ufficio principale e dal secondo ufficio. Ogni ufficio ha un proprio Session Border Controller (SBC) connesso a un gestore PSTN.  
 
In questo paese, Contoso aveva configurato LBR per la distribuzione di Skype for Business. Per determinare come configurare LBR per Teams, Contoso legge il piano [Location-Based routing per il routing diretto.](location-based-routing-plan.md) Contoso ha determinato che Teams e Skype for Business seguono gli stessi scenari in cui è possibile effettuare una chiamata, quando può essere ricevuta, quando una chiamata PSTN può essere trasferita a un utente di Teams e quando è possibile trasferire un altro utente di Teams alla chiamata PSTN.  

Per Skype for Business, la rete LBR è stata configurata con il trunk SIP di Session Border Controller (SBC) che si connette al gestore PSTN. Per questo SBC, Contoso ha esaminato l'elenco di [SBC](direct-routing-border-controllers.md) certificati e determinato che il servizio SBC distribuito è certificato per l'instradamento diretto, ma non è certificato per Media Bypass. Per supportare LBR, il routing diretto deve essere configurato per il servizio SBC in locale, deve esserci un punto di uscita Internet locale e SBC deve essere configurato per media bypass. Sulla base di queste informazioni, Contoso ha deciso quanto segue:

- Per posticipare l'abilitazione di Teams LBR finché l'SBC esistente non viene certificato per Media Bypass.   

- Contoso ha deciso di usare il sito principale SBC per la route diretta a Office 365.  Il sito principale SBC sarà il proxy SBC per il sito remoto.  

- Contoso ha usato un consulente di terze parti in India per fornire assistenza nella certificazione della configurazione LBR con la società di telefonia del paese.  

- Per supportare gli utenti che lavorano dall'esterno dell'ufficio per effettuare chiamate PSTN, ai dipendenti è stato fornito un telefono cellulare rilasciato dalla società. 

I diagrammi seguenti mostrano le distribuzioni prima e dopo per un paese con normative di telefonia che richiedono Location-Based distribuzione:

**Distribuzione originale**

![Diagramma che mostra lo stato precedente](media/voice-case-study-5.png)

**Distribuzione con routing diretto**

![Diagramma che mostra lo stato precedente](media/voice-case-study-6.png)


## <a name="configuration"></a>Configurazione: 

Per configurare i componenti di rete in Teams, Contoso ha seguito le istruzioni in Gestire la topologia [di rete per le funzionalità vocali del cloud.](manage-your-network-topology.md) Contoso ha completato i passaggi seguenti per configurare Location-Based distribuzione: 

- Definire le aree di rete: è stata definita un'area di rete. 

- Definizione dei siti di rete: sono stati definiti due siti di rete. Un sito per ogni ufficio dell'area geografica.

- Definire le subnet di rete: ogni piano all'interno di una sede ha la propria subnet per la rete cablata e wireless. Questa configurazione ha comportato 20 subnet per Contoso. 

- Definire indirizzi IP attendibili: gli indirizzi IP esterni per SBC sono stati aggiunti all'indirizzo IP attendibile.  

