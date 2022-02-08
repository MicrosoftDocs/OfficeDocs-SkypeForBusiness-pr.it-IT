---
title: Configurare l'integrazione con Exchange di archiviazione per Skype for Business Server
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 8f48b87f-a57f-4ed8-8c79-5c75b316b696
description: "Riepilogo: leggere questo argomento per informazioni su come configurare l'integrazione con Exchange archiviazione in Skype for Business Server."
ms.openlocfilehash: f1b6c028622edfe726b32f5fc4788668aaf4e51e
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/05/2022
ms.locfileid: "62393438"
---
# <a name="configure-integration-with-exchange-storage-for-skype-for-business-server"></a>Configurare l'integrazione con Exchange di archiviazione per Skype for Business Server
 
**Riepilogo:** Leggere questo argomento per informazioni su come configurare l'integrazione con Exchange archiviazione in Skype for Business Server.
  
Se si utilizza l'integrazione di Microsoft Exchange per tutti gli utenti nella distribuzione, non è necessario configurare i criteri di Skype for Business Server di archiviazione per gli utenti. È invece possibile configurare i Exchange In-Place di archiviazione per supportare l'archiviazione per gli utenti ospitati in Exchange, con le cassette postali In-Place conservazione. Prima di configurare l'integrazione con Exchange archiviazione, vedere [Plan for archiving in Skype for Business Server](../../plan-your-deployment/archiving/archiving.md). Per informazioni dettagliate Exchange In-Place criteri di blocco, vedere la documentazione Exchange prodotto. 
  
## <a name="configure-integration-with-microsoft-exchange-storage"></a>Configurare l'integrazione con Microsoft Exchange storage

1. Da un account utente assegnato al ruolo CsArchivingAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.
    
2. Aprire una finestra del browser e quindi immettere l'URL dell'amministratore per aprire il Skype for Business Server di controllo. 
    
3. Nella barra di navigazione di sinistra fare clic su **Monitoraggio e archiviazione**, quindi scegliere **Configurazione archiviazione**.
    
4. Fare clic sul nome della configurazione globale, del sito o del pool appropriata nell'elenco delle configurazioni di archiviazione, fare clic su **Modifica**, su **Mostra dettagli** e quindi eseguire le operazioni seguenti:
    
   - Per abilitare l'integrazione con Exchange archiviazione, selezionare la **casella di controllo Integrazione Exchange Microsoft**.
    
   - Per disabilitare l'integrazione Exchange archiviazione, deselezionare la **casella di controllo Integrazione Exchange Microsoft**.
    
5. Fare clic su **Commit**.
    
## <a name="when-skype-for-business-server-and-microsoft-exchange-are-deployed-in-different-forests"></a>Quando Skype for Business Server e Microsoft Exchange distribuiti in foreste diverse

Se si utilizza l'integrazione di Microsoft Exchange e Microsoft Exchange Server non viene distribuito nella stessa foresta di Skype for Business Server, è necessario assicurarsi che i seguenti attributi di Active Directory di Exchange siano sincronizzati con la foresta in cui Skype for Business Server distribuito:
  
- msExchUserHoldPolicies
    
- proxyAddresses
    
Si tratta di un attributo a valore multiplo. Quando si sincronizza questo attributo, è necessario unire i valori, e non sostituirli, per evitare che i valori esistenti vengano persi.
  

