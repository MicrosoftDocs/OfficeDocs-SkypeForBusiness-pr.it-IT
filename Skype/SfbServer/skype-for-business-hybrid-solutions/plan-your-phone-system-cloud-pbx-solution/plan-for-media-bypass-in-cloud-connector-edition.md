---
title: Pianificare il bypass multimediale in Cloud Connector Edition
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 11/15/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: e69ac58c-e8fe-40bc-a4c8-f0a0190fbaa7
description: Leggere questo argomento per esaminare le considerazioni sulla pianificazione per l'implementazione del bypass multimediale con Cloud Connector Edition versione 2.0 e successive. Per informazioni sulla distribuzione del bypass multimediale, vedere Deploy media bypass in Cloud Connector Edition.
ms.openlocfilehash: bae10c77a6b382eaca7189ed6ae52960a6fb1bf9
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51096200"
---
# <a name="plan-for-media-bypass-in-cloud-connector-edition"></a>Pianificare il bypass multimediale in Cloud Connector Edition
 
Leggere questo argomento per esaminare le considerazioni sulla pianificazione per l'implementazione del bypass multimediale con Cloud Connector Edition versione 2.0 e successive. Per informazioni sulla distribuzione del bypass multimediale, vedere [Deploy media bypass in Cloud Connector Edition.](deploy-media-bypass-in-cloud-connector.md)
  
Il bypass multimediale consente a un client di inviare contenuti multimediali direttamente all'hop successivo PSTN (Public Switched Telephone Network), un gateway o session border controller (SBC), ed eliminare il componente Cloud Connector Edition dal percorso multimediale.
  
Il bypass multimediale può migliorare la qualità vocale riducendo la latenza, la possibilità di perdita di pacchetti e il numero di punti di potenziale errore. L'eliminazione dell'elaborazione multimediale per le chiamate ignorate riduce il carico su Cloud Connector, che consente un numero maggiore di chiamate simultanee e può migliorare la scalabilità. 
  
 Se si libera Cloud Connector dalle attività di elaborazione multimediale, è possibile ridurre il numero di appliance Cloud Connector richieste da un'infrastruttura, pertanto è consigliabile abilitare il bypass multimediale quando possibile.
  
## <a name="how-media-bypass-affects-media-and-signaling-pathways"></a>In che modo il bypass multimediale influisce sui percorsi multimediali e di segnalazione

Mentre la segnalazione prende lo stesso percorso con o senza bypass multimediale, il flusso multimediale sarà diverso. I diagrammi seguenti mostrano i percorsi multimediali e di segnalazione nelle topologie con e senza bypass multimediale. 
  
Ad esempio, nella topologia seguente, che non utilizza il bypass multimediale, un client Skype for Business esegue una chiamata PSTN a un numero esterno, la segnalazione SIP passa a Microsoft 365 o Office 365, che indirizza il traffico di segnalazione in base ai criteri vocali dell'utente finale. Per gli utenti di Cloud Connector, il criterio vocale indirizza il traffico di segnalazione al server perimetrale del connettore cloud, che quindi instrada il traffico di segnalazione a un SBC (Session Border Controller) PSTN o a un gateway tramite il Mediation Server cloud Connector. I flussi multimediali dal client Skype for Business al Mediation Server cloud Connector e quindi al servizio SBC o al gateway, come illustrato nel diagramma seguente:
  
**Percorsi multimediali e di segnalazione senza bypass multimediale**

![segnalazione senza bypass multimediale](../../media/5cd7e3bf-2565-4bd9-ad5a-f03e13c01060.png)
  
Una chiamata in ingresso dalla rete PSTN utilizza lo stesso percorso di segnalazione nella direzione inversa. Per gli utenti interni, i supporti verranno comunque in ultima analisi fluire tra il client Skype for Business e il Mediation Server del connettore cloud e quindi il servizio SBC o il gateway.
  
Nella topologia successiva, che utilizza il bypass multimediale, la segnalazione ha lo stesso percorso, ma i flussi multimediali direttamente tra il client Skype for Business e il gateway o SBC, come illustrato nel diagramma seguente:
  
**Percorsi multimediali e di segnalazione con bypass multimediale**

![segnalazione con bypass multimediale](../../media/60400c38-4921-4964-89f2-5e53b68fb497.png)
  
## <a name="multi-site-scenario-and-media-bypass"></a>Scenario multis sito e bypass multimediale

Il bypass multimediale è utile anche quando si desidera fornire servizi di telefonia a più siti utilizzando un singolo dispositivo Cloud Connector. Poiché Cloud Connector non è in grado di instradare le chiamate in base ai numeri di origine o di destinazione, la maggior parte delle aziende distribuisce un SBC o un gateway dietro Cloud Connector per prendere decisioni di routing. Il bypass multimediale in questo scenario elimina l'hop tra il client e il controller SBC centrale o il gateway, come illustrato nel diagramma seguente:
  
**Applicazione multis sito**

![Esempio di cloud connector multisito](../../media/ace8dc3c-1082-46a2-b8b4-98cbf678620e.png)
  
1. Il traffico SIP passa dall'utente di Zurigo a Microsoft 365 o Office 365.
    
2. Il traffico viene quindi instradato all'appliance Cloud Connector di Amsterdam come specificato nel criterio di routing vocale dell'utente.
    
3. L'appliance Cloud Connector di Amsterdam invia il traffico SIP al gateway centrale di Amsterdam.
    
4. Il gateway centrale di Amsterdam prende le decisioni di routing appropriate e quindi invia il traffico a un SBC o a un gateway a Zurigo, mentre i contenuti multimediali fluino direttamente tra il client Skype for Business e SBC o il gateway di Amsterdam.
    
   Questo approccio consente di servire più utenti per una distribuzione di Cloud Connector in cui Cloud Connector è centralizzato. Anche se Cloud Connector viene eliminato dal percorso multimediale, in uno scenario multisito centralizzato i supporti possono comunque attraversare la rete WAN due volte come richiesto per il flusso attraverso il gateway o SBC centralizzato.
  
Se un client si trova all'esterno della rete aziendale effettuando una chiamata in uscita, il traffico multimediale passa attraverso i server Perimetrali e Mediation Server di Cloud Connector e il collegamento WAN tra Zurigo e Amsterdam, come illustrato nel diagramma seguente:
  
![Esempio di cloud connector multisito 2](../../media/ef95839c-4552-440e-9698-7615707a1b50.png)
  
## <a name="supported-clients-for-media-bypass"></a>Client supportati per il bypass multimediale

Con la prima versione del bypass multimediale, l'unico client supportato è skype for business 2016 Windows Client che fa parte di Microsoft 365 Apps for enterprise, versione 16.0.7870.2020 o successiva. I clienti possono usare qualsiasi canale: Current, Deferred o First Release Deferred. 
  
> [!NOTE]
> Se si utilizza una soluzione VPN client in combinazione con il client Skype for Business, il bypass multimediale è supportato solo con una configurazione split tunnel VPN. 
  
Per ulteriori informazioni sui canali di rilascio, vedere Panoramica dei canali di aggiornamento [per Microsoft 365 Apps for enterprise.](https://support.office.com/article/Overview-of-update-channels-for-Office-365-ProPlus-9ccf0f13-28ff-4975-9bd2-7e4ea2fefef4?ui=en-US&amp;rs=en-US&amp;ad=US)
  
Per la versione corrente dei client in canali diversi, vedere Informazioni sulla versione per gli aggiornamenti [a Microsoft 365 Apps for enterprise.](/officeupdates/release-notes-office365-proplus) 
  
## <a name="cloud-connector-capacity-considerations-with-media-bypass"></a>Considerazioni sulla capacità del connettore cloud con bypass multimediale

Senza bypass multimediale e a seconda dell'hardware, un'appliance Cloud Connector può gestire da 50 a 500 chiamate simultanee che richiedono supporti per il viaggio attraverso un Mediation Server. Per ulteriori informazioni, vedere [Piano per Skype for Business Cloud Connector Edition](./plan-skype-for-business-cloud-connector-edition.md). 
  
Con il bypass multimediale abilitato, i client interni nella versione supportata non utilizzano Mediation Server, quindi il numero di client interni può aumentare in modo significativo. 
  
Come indicato in precedenza, i client esterni o i client non supportati utilizzeranno i server Edge e Mediation Server del connettore cloud per i supporti. Quando si calcola il numero di appliance Cloud Connector da inserire in un sito, è necessario considerare il traffico proveniente da utenti esterni e utenti su client non supportati.
  
## <a name="cloud-connector-supports-always-bypass-mode"></a>Cloud Connector supporta la modalità Bypass sempre

Cloud Connector supporta solo la modalità Bypass always. Negli ambienti locali sono disponibili due opzioni: Ignora sempre e Usa informazioni sito e area geografica.
  
Ignora sempre significa che verrà tentato il bypass multimediale per tutte le chiamate PSTN con client interni come punto di origine o di destinazione. Per determinare se il client è interno o esterno, viene utilizzato un sito Web nella macchina virtuale mediation server. Se il client può raggiungere il sito, viene considerato interno e viene utilizzato il bypass multimediale. Se il client non riesce a raggiungere il sito (ad esempio, il client si trova in una rete domestica), non viene utilizzato il bypass multimediale. 
  
Always Bypass richiede una connettività senza problemi tra gli utenti e i gateway PSTN all'interno di un sito PSTN. 
  
Per ulteriori informazioni, vedere [Piano per Skype for Business Cloud Connector Edition](./plan-skype-for-business-cloud-connector-edition.md). 
  
Ad esempio, nel diagramma seguente, gli utenti europei devono essere ben connessi ai tre Session Border Controller (SBC) di Amsterdam, mentre gli utenti us west devono essere ben connessi ai due SBC di Seattle. Ben connessi significa che si trovano negli stessi siti di rete dei SBC o dei gateway oppure tramite collegamenti WAN con larghezza di banda appropriata.
  
![Capacità del connettore cloud](../../media/efb2269b-d44f-474e-aea8-c5158e729cfe.png)
  
> [!NOTE]
> Se un utente da Zurigo si reca nell'ufficio di Seattle e si desidera utilizzare la rete interna per recapitare il traffico multimediale tra l'utente in viaggio e i gateway in Europa (anziché passare attraverso Internet), è necessario assicurarsi che l'ufficio di Seattle e l'ufficio di Amsterdam in cui si trovano i gateway o gli SBC europei siano idonei e connessi. 
  
## <a name="codecs-used-in-media-bypass"></a>Codec utilizzati nel bypass multimediale

Con il bypass multimediale abilitato, il traffico multimediale tra un client e un SBC o un gateway utilizza il codec G.711. 
  
## <a name="see-also"></a>Vedere anche

[Distribuire il bypass multimediale in Cloud Connector Edition](deploy-media-bypass-in-cloud-connector.md)