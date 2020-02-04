---
title: Configurazione delle notifiche push del client mobile
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.lscp.ClientPushNotificationCfgMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b7a85d75-9d36-4980-b669-2a009799d905
description: Per configurare le notifiche push Microsoft e le notifiche push di Apple, è necessario creare un criterio per definire i tipi di notifica push necessari.
ms.openlocfilehash: 36cf19d42a2378e024f90d3dbe60123b3d5473fa
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/03/2020
ms.locfileid: "41700031"
---
# <a name="mobile-client-push-notification-configuration"></a>Client mobile: configurazione di notifiche push
 
Per configurare le **notifiche push Microsoft** e le **notifiche push di Apple**, è necessario creare un criterio per definire i tipi di notifica push necessari.
  
Nella schermata principale di configurazione è possibile fare clic su **Aggiorna** per aggiornare e ripopolare l'elenco dei criteri. Viene fornita una casella di ricerca per limitare l'elenco dei criteri visualizzati. Quando si digita il nome che si sta cercando, l'elenco dei criteri si restringe automaticamente.
  
> [!IMPORTANT]
> Le impostazioni dei criteri applicate a un livello di criteri possono eseguire l'override delle impostazioni applicate a un altro livello di criteri. La precedenza dei criteri è: criteri utente (la maggior parte delle influenze) esegue l'override di un criterio del sito e quindi un criterio del sito sostituisce un criterio globale (almeno l'influenza). Ciò significa che l'impostazione del criterio è più vicina all'oggetto che il criterio sta influenzando, più influenza ha sull'oggetto. 
  
Sono disponibili due selezioni per la creazione e la modifica dei criteri:
  
1. **Nuovo**: fare clic per creare un nuovo criterio. È necessario specificare un sito per cui applicare i criteri. Le impostazioni per la notifica push vengono quindi configurate. Per la **configurazione delle notifiche push**, è possibile creare solo criteri per i siti già creati.
    
2. **Modifica**: selezionare un criterio e fare clic su modifica per selezionare un'azione da un elenco a discesa. È possibile modificare solo i siti già creati o modificare i criteri globali:
    
   - **Mostra dettagli...**: Visualizza le informazioni sui criteri attualmente selezionati. Sarà possibile apportare modifiche ai criteri esistenti.
    
   - **Selezionare tutto**: se si hanno diversi criteri e occorre selezionare tutti i criteri, fare clic su Seleziona tutto
    
   - **Elimina**: verrà rimosso il criterio selezionato. Se si usa **Seleziona tutto** ed **Elimina** verranno rimossi tutti i criteri
    
     > [!NOTE]
     > Non è possibile eliminare i criteri **globali** predefiniti. Se si tenta di eliminarlo, verrà visualizzato un avviso che indica che i criteri globali sono stati restituiti ai valori predefiniti, ovvero tutte le impostazioni sono deselezionate, ma non è possibile rimuoverlo.
  
La creazione di un nuovo criterio o la modifica di un criterio esistente è associata a due azioni:
  
- **Commit** L'azione di commit crea o aggiorna il criterio e salva le modifiche
    
- **Annulla** L'azione Annulla Elimina tutte le modifiche apportate dopo l'ultima azione di commit. Se si Annulla, le modifiche apportate andranno perse.
    
Sono possibili due impostazioni per la **configurazione della notifica push**. Le impostazioni sono associate ai servizi di notifica push per Microsoft e per Apple. È possibile abilitare la notifica push per un servizio qualsiasi selezionando la casella di controllo accanto al nome del servizio. Per deselezionare la casella di controllo, è possibile selezionarla. Dopo aver eseguito le selezioni, è possibile eseguire il commit o l'annullamento. Se si fa clic su commit, le modifiche apportate al criterio verranno salvate.
  

