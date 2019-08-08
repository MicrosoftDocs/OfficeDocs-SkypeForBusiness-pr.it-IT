---
title: Configurare l'integrazione con lo spazio di archiviazione di Exchange per Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8f48b87f-a57f-4ed8-8c79-5c75b316b696
description: "Riepilogo: leggere questo argomento per informazioni su come configurare l'integrazione con lo spazio di archiviazione di Exchange in Skype for Business Server."
ms.openlocfilehash: 72caf77c81dae538f793afe6f0a94ad6b61d0fa5
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/07/2019
ms.locfileid: "36234547"
---
# <a name="configure-integration-with-exchange-storage-for-skype-for-business-server"></a>Configurare l'integrazione con lo spazio di archiviazione di Exchange per Skype for Business Server
 
**Riepilogo:** Leggere questo argomento per informazioni su come configurare l'integrazione con lo spazio di archiviazione di Exchange in Skype for Business Server.
  
Se si usa l'integrazione di Microsoft Exchange per tutti gli utenti della distribuzione, non è necessario configurare i criteri di archiviazione di Skype for Business Server per gli utenti. Puoi invece configurare i criteri di blocco sul posto di Exchange per supportare l'archiviazione per gli utenti ospitati in Exchange, con le cassette postali inserite sul posto. Prima di configurare l'integrazione con lo spazio di archiviazione di Exchange, leggere [piano per l'archiviazione in Skype for Business Server](../../plan-your-deployment/archiving/archiving.md). Per informazioni dettagliate sui criteri di blocco sul posto di Exchange, vedere la documentazione del prodotto Exchange. 
  
## <a name="configure-integration-with-microsoft-exchange-storage"></a>Configurare l'integrazione con lo spazio di archiviazione di Microsoft Exchange

1. Da un account utente assegnato al ruolo CsArchivingAdministrator o CsAdministrator, accedere a qualsiasi computer della distribuzione interna.
    
2. Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Skype for Business Server. 
    
3. Sulla barra di spostamento sinistra fare clic su **monitoraggio e archiviazione**e quindi su **Configurazione archiviazione**.
    
4. Fare clic sul nome della configurazione globale, del sito o del pool appropriata nell'elenco delle configurazioni di archiviazione, fare clic su **modifica**, fare clic su **Mostra dettagli**e quindi eseguire le operazioni seguenti:
    
   - Per abilitare l'integrazione con l'archiviazione di Exchange, selezionare la casella di controllo **integrazione di Microsoft Exchange** .
    
   - Per disabilitare l'integrazione con l'archiviazione di Exchange, deselezionare la casella di controllo **integrazione di Microsoft Exchange** .
    
5. Fare clic su **Commit**.
    
## <a name="when-skype-for-business-server-and-microsoft-exchange-are-deployed-in-different-forests"></a>Quando Skype for Business Server e Microsoft Exchange vengono distribuiti in foreste diverse

Se si usa l'integrazione di Microsoft Exchange e Microsoft Exchange Server non è distribuito nella stessa foresta di Skype for Business Server, è necessario verificare che gli attributi di Exchange Active Directory seguenti siano sincronizzati con la foresta in cui Skype for Server aziendale distribuito:
  
- msExchUserHoldPolicies
    
- proxyAddresses
    
Questo è un attributo multivalore. Quando si sincronizza questo attributo, è necessario unire i valori, non sostituirli per evitare che i valori esistenti vengano persi.
  

