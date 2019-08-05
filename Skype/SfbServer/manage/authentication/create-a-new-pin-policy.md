---
title: Creare un nuovo criterio PIN in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 8bdf0478-fe9f-4371-93ff-db39381a25db
description: 'Riepilogo: creare un nuovo criterio PIN in Skype for Business Server.'
ms.openlocfilehash: aaedcbfe28cb8e64b4adf7a302eef8c0d3d08a1f
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36189683"
---
# <a name="create-a-new-pin-policy-in-skype-for-business-server"></a>Creare un nuovo criterio PIN in Skype for Business Server
 
**Riepilogo:** Creare un nuovo criterio PIN in Skype for Business Server.
  
È possibile usare la pagina dei **criteri PIN** per specificare l'autenticazione PIN (Personal Identification Number) per gli utenti che si connettono a Skype for business con telefoni IP. Per usare l'autenticazione PIN, verificare che **l'opzione Abilita autenticazione PIN** sia selezionata nelle impostazioni del servizio Web.
  
Seguire questa procedura per creare un criterio PIN a livello di utente o a livello di sito. 
  
### <a name="to-create-a-user-or-site-pin-policy"></a>Per creare un criterio PIN per un utente o un sito

1.  Da un account utente che è un membro del gruppo RTCUniversalServerAdmins (o ha diritti utente equivalenti) o assegnato al ruolo CsServerAdministrator o CsAdministrator, accedere a qualsiasi computer presente nella rete in cui è stato distribuito Skype for Business Server. .
    
2. Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Skype for Business Server. 
    
3. Sulla barra di spostamento sinistra fare clic su **sicurezza** e quindi su **criteri PIN**.
    
4. Nella pagina **criteri PIN** fare clic su **nuovo**e quindi eseguire una delle operazioni seguenti:
    
   - Per creare un criterio a livello di utente, fare clic su **criteri utente**. In **nome**digitare un nome che descriva il criterio in **nuovo criterio PIN**.
    
   - Per creare un criterio a livello di sito, fare clic su **criteri sito**. Nel campo **Seleziona ricerca sito** digitare tutto o parte del nome del sito per cui si vuole creare un criterio. Nell'elenco dei siti risultante fare clic sul sito desiderato e quindi fare clic su **OK**.
    
5. Nel campo **Descrizione** Digitare una descrizione del criterio PIN.
    
6. Nel campo **lunghezza minima PIN** Digitare o selezionare la lunghezza minima del PIN che si vuole consentire. La lunghezza minima predefinita è di cinque cifre.
    
7. Per poter specificare il numero massimo di tentativi di accesso prima che un utente venga bloccato, selezionare la casella di controllo **specifica tentativi di accesso massimo** . Se non si seleziona questa opzione, il numero massimo di tentativi consentiti viene determinato automaticamente in base alla lunghezza del PIN. Per impostazione predefinita, il numero massimo di tentativi viene determinato automaticamente.
    
8. Se è stata selezionata la casella di controllo **specifica tentativi di accesso massimo** , in **tentativi di accesso massimo**digitare o selezionare il numero massimo di tentativi di accesso che si desidera consentire.
    
9. Per impostare i pin in scadenza, selezionare la casella di controllo **Abilita scadenza PIN** . Se non si seleziona questa opzione, i pin non scadono mai. Per impostazione predefinita, i pin non scadono mai.
    
10. Se è stata selezionata la casella di controllo **Abilita scadenza PIN** , in **PIN scade dopo (giorni)** digitare o selezionare il numero di giorni dopo il quale i pin scadono.
    
11. In **conteggio cronologia PIN**Digitare il numero di pin che un utente deve creare prima che l'utente possa riutilizzare un PIN. Per impostazione predefinita, gli utenti possono riutilizzare i loro PIN.
    
12. Per consentire modelli comuni di cifre nei pin, ad esempio "1234" e "8888", selezionare la casella di controllo **Consenti schemi comuni** . Se non si seleziona questa opzione, sono consentiti solo modelli complessi di cifre. Per impostazione predefinita, sono consentiti solo modelli complessi di cifre.
    
    > [!IMPORTANT]
    > È consigliabile non consentire modelli comuni. 
  
13. Fare clic su **Commit**.
    

