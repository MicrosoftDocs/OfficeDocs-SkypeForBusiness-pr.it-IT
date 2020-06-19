---
title: Case Study di teams Voice contoso
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
description: Case Study di teams Voice per società multinazionali
appliesto:
- Microsoft Teams
ms.openlocfilehash: f1ba92794b2ba17cc23e1bca55800c9307707636
ms.sourcegitcommit: af15d99837a389b6b26952211e65cd68c4b7f46e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/18/2020
ms.locfileid: "44786006"
---
# <a name="contoso-case-study-location-based-routing"></a>Case Study di Contoso: routing basato sulla posizione

Il routing basato sulla posizione (LBR) è una funzionalità che limita l'esclusione dei pedaggi in base ai criteri e alla posizione fisica dell'utente al momento dell'immissione o della ricezione di una chiamata.  

## <a name="overview"></a>Panoramica

Contoso ha due uffici in un paese in cui è illegale ignorare il provider PSTN (Public Switched Telephone Network) per diminuire i costi delle chiamate interurbane. L'ufficio principale ha una connessione Internet usata dall'ufficio principale e dal secondo ufficio. Ogni Office ha il proprio session border controller (SBC) connesso a un gestore PSTN.  
 
In questo paese, Contoso ha configurato LBR per la distribuzione di Skype for business. Per determinare come configurare LBR per Teams, contoso Read [routing basato sulla posizione del piano per il routing diretto](location-based-routing-plan.md). Contoso ha determinato che i team e Skype for business seguono gli stessi scenari in cui può essere inserita una chiamata, quando può essere ricevuta, quando è possibile trasferire una chiamata PSTN a un utente di teams e quando è possibile trasferire un altro utente di teams alla chiamata PSTN.  

Per Skype for business, LBR è stato configurato con il trunk SIP Session Border Controller (SBC) che si connette al gestore PSTN. Per questo SBC, Contoso ha esaminato l' [elenco di sbcs certificati](direct-routing-border-controllers.md) e ha determinato che SBC distribuito è certificato per il routing diretto ma non è certificato per il bypass multimediale. Per supportare LBR, il routing diretto deve essere configurato per il SBC in loco, deve essere disponibile un'uscita Internet locale e il SBC deve essere configurato per il bypass multimediale. In base a queste informazioni, Contoso ha deciso quanto segue:

- Per ritardare l'abilitazione di teams LBR fino a quando l'attuale SBC non è certificato per il bypass multimediale.   

- Contoso ha deciso di usare il SBC del sito principale per la route Direct a Office 365.  Il SBC del sito principale sarà l'SBC proxy per il sito remoto.  

- Contoso ha usato un consulente di terze parti basato in India per facilitare la certificazione della configurazione di LBR con la società di telefonia in un paese.  

- Per supportare gli utenti che lavorano dall'esterno dell'ufficio per effettuare chiamate PSTN, il telefono cellulare rilasciato dalla società è stato fornito ai dipendenti. 

I diagrammi seguenti mostrano le distribuzioni prima e dopo per un paese con regole per la telefonia che richiedono il routing basato sulla posizione:

**Distribuzione originale**

![Diagramma che mostra prima dello stato](media/voice-case-study-5.png)

**Distribuzione con routing diretto**

![Diagramma che mostra prima dello stato](media/voice-case-study-6.png)


## <a name="configuration"></a>Configurazione 

Per configurare i componenti di rete in teams, Contoso ha seguito le istruzioni in [gestire la topologia di rete per le funzionalità vocali di cloud](manage-your-network-topology.md). Contoso ha completato la procedura descritta di seguito per configurare il routing basato sulla posizione: 

- Definire le aree di rete-è stata definita un'area di rete. 

- Definire i siti di rete: sono stati definiti due siti di rete. Un sito per ogni posizione di Office nell'area geografica.

- Definire le subnet di rete: ogni piano all'interno di una posizione di Office ha la propria subnet per la rete cablata e wireless. Questa configurazione ha generato 20 subnet per contoso. 

- Definire indirizzi IP attendibili: gli indirizzi IP di fronte esterno per il SBC sono stati aggiunti all'indirizzo IP attendibile.  

