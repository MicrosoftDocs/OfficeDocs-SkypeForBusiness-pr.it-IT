---
title: Modificare un criterio PIN esistente in Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 517caaee-3349-4fa6-8d86-e4da3258a445
description: 'Riepilogo: modificare un criterio PIN esistente in Skype for Business Server.'
ms.openlocfilehash: dac6540407ed019fe9147d86bc119426a6679574
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/04/2021
ms.locfileid: "60754869"
---
# <a name="modify-an-existing-pin-policy-in-skype-for-business-server"></a>Modificare un criterio PIN esistente in Skype for Business Server
 
**Riepilogo:** Modificare un criterio PIN esistente in Skype for Business Server.
  
È possibile utilizzare la **scheda Criteri PIN** per fornire l'autenticazione PIN (Personal Identification Number) agli utenti che si connettono a Skype for Business telefoni IP. Per utilizzare l'autenticazione tramite PIN, verificare che sia selezionata l'opzione **Abilita autenticazione PIN** nelle impostazioni relative ai servizi Web.
  
Eseguire questa procedura per modificare un criterio PIN a livello di utente o di sito. 
  
### <a name="to-modify-an-existing-pin-policy"></a>Per modificare un criterio PIN esistente

1.  Da un account utente membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) o assegnato al ruolo CsServerAdministrator o CsAdministrator, accedere a qualsiasi computer nella rete in cui è stato distribuito Skype for Business Server.
    
2. Apri una finestra del browser e quindi immetti l'URL di amministratore per aprire il Pannello Skype for Business Server controllo. 
    
3. Sulla barra di spostamento sinistra fare clic su **Sicurezza** e quindi su **Criteri PIN**.
    
4. Nella pagina **Criteri PIN** fare clic su criterio, fare clic su **Modifica** e quindi su **Mostra dettagli**.
    
5. In **Modifica criterio PIN**, in **Lunghezza minima PIN**, digitare o selezionare la lunghezza minima che si desidera consentire per il PIN. La lunghezza minima predefinita è di cinque cifre.
    
6. Per poter specificare il numero massimo di tentativi di accesso prima che un utente venga bloccato, selezionare la casella di controllo **Specifica numero massimo di tentativi di accesso**. Se non si seleziona questa opzione, il numero massimo di tentativi consentiti viene determinato automaticamente in base alla lunghezza del PIN. Per impostazione predefinita, il numero massimo di tentativi viene determinato automaticamente.
    
7. Se si seleziona la casella di controllo **Specifica numero massimo di tentativi di accesso**, in **Numero massimo di tentativi di accesso** digitare o selezionare il numero massimo di tentativi di accesso che si desidera consentire.
    
8. Per impostare una scadenza per i PIN, selezionare la casella di controllo **Abilita scadenza PIN**. Se non si seleziona questa opzione, i PIN non scadranno mai, come da impostazione predefinita.
    
9. Se si seleziona la casella di controllo **Abilita scadenza PIN**, in **Scadenza PIN dopo (giorni)** digitare o selezionare il numero di giorni trascorsi i quali scadranno i PIN.
    
10. In **Conteggio cronologia PIN** digitare il numero di PIN che deve creare un utente prima che possa riutilizzare un PIN. Per impostazione predefinita, gli utenti possono riutilizzare i loro PIN.
    
11. Per consentire schemi comuni di cifre nei PIN, ad esempio numeri progressivi o gruppi ripetuti di numeri, selezionare la casella di controllo **Consenti formati comuni**. Se non si seleziona questa opzione, saranno consentiti solo schemi complessi di cifre, come da impostazione predefinita.
    
    > [!IMPORTANT]
    > È consigliabile evitare di consentire i formati comuni. 
  
12. Fare clic su **Commit**.
    

