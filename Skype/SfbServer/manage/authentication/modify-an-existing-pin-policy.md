---
title: Modificare un criterio PIN esistente in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 517caaee-3349-4fa6-8d86-e4da3258a445
description: 'Riepilogo: modificare un criterio PIN esistente in Skype for Business Server.'
ms.openlocfilehash: 91ed45efb96c3eb9c2bb114b5d5b8f25d0e00f93
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818778"
---
# <a name="modify-an-existing-pin-policy-in-skype-for-business-server"></a>Modificare un criterio PIN esistente in Skype for Business Server
 
**Riepilogo:** Modificare un criterio PIN esistente in Skype for Business Server.
  
Puoi usare la scheda **criteri PIN** per specificare l'autenticazione PIN (Personal Identification Number) per gli utenti che si connettono a Skype for business con telefoni IP. Per usare l'autenticazione PIN, verificare che **l'opzione Abilita autenticazione PIN** sia selezionata nelle impostazioni del servizio Web.
  
Seguire questa procedura per modificare un criterio PIN a livello di utente o a livello di sito. 
  
### <a name="to-modify-an-existing-pin-policy"></a>Per modificare un criterio PIN esistente

1.  Da un account utente che è un membro del gruppo RTCUniversalServerAdmins (o ha diritti utente equivalenti) o assegnato al ruolo CsServerAdministrator o CsAdministrator, accedere a qualsiasi computer presente nella rete in cui è stato distribuito Skype for Business Server. .
    
2. Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Skype for Business Server. 
    
3. Sulla barra di spostamento sinistra fare clic su **sicurezza** e quindi su **criteri PIN**.
    
4. Nella pagina **criteri PIN** fare clic su un criterio, fare clic su **modifica**e quindi su **Mostra dettagli**.
    
5. In **modifica criterio PIN**, in **lunghezza minima PIN**, digitare o selezionare la lunghezza minima del PIN che si vuole consentire. La lunghezza minima predefinita è di cinque cifre.
    
6. Per poter specificare il numero massimo di tentativi di accesso prima che un utente venga bloccato, selezionare la casella di controllo **specifica tentativi di accesso massimo** . Se non si seleziona questa opzione, il numero massimo di tentativi consentiti viene determinato automaticamente in base alla lunghezza del PIN. Per impostazione predefinita, il numero massimo di tentativi viene determinato automaticamente.
    
7. Se è stata selezionata la casella di controllo **specifica tentativi di accesso massimo** , in **tentativi di accesso massimo**digitare o selezionare il numero massimo di tentativi di accesso che si desidera consentire.
    
8. Per impostare i pin in scadenza, selezionare la casella di controllo **Abilita scadenza PIN** . Se non si seleziona questa opzione, i pin non scadono mai. Per impostazione predefinita, i pin non scadono mai.
    
9. Se è stata selezionata la casella di controllo **Abilita scadenza PIN** , in **PIN scade dopo (giorni)** digitare o selezionare il numero di giorni dopo il quale i pin scadono.
    
10. In **conteggio cronologia PIN**Digitare il numero di pin che un utente deve creare prima che l'utente possa riutilizzare un PIN. Per impostazione predefinita, gli utenti possono riutilizzare i loro PIN.
    
11. Per consentire modelli comuni di cifre nei pin, ad esempio numeri sequenziali e set ripetitivi di numeri, selezionare la casella di controllo **Consenti schemi comuni** . Se non si seleziona questa opzione, sono consentiti solo modelli complessi di cifre. Per impostazione predefinita, sono consentiti solo modelli complessi di cifre.
    
    > [!IMPORTANT]
    > È consigliabile non consentire modelli comuni. 
  
12. Fare clic su **Commit**.
    

