---
title: Creare un nuovo criterio PIN in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 8bdf0478-fe9f-4371-93ff-db39381a25db
description: 'Riepilogo: creare un nuovo criterio PIN in Skype for Business Server.'
ms.openlocfilehash: b0d1be74e509fbaddfc59250f4f5ce05a2021260
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49828406"
---
# <a name="create-a-new-pin-policy-in-skype-for-business-server"></a>Creare un nuovo criterio PIN in Skype for Business Server
 
**Riepilogo:** Creare un nuovo criterio PIN in Skype for Business Server.
  
È possibile utilizzare la pagina **criteri PIN** per fornire l'autenticazione PIN (Personal Identification Number) agli utenti che si connettono a Skype for business con i telefoni IP. Per utilizzare l'autenticazione tramite PIN, verificare che sia selezionata l'opzione **Abilita autenticazione PIN** nelle impostazioni relative ai servizi Web.
  
Per creare criteri PIN a livello di utente o di sito, eseguire la procedura seguente. 
  
### <a name="to-create-a-user-or-site-pin-policy"></a>Per creare criteri PIN a livello di utente o sito

1.  Da un account utente membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) oppure assegnato al ruolo CsServerAdministrator o CsAdministrator, eseguire l'accesso a qualsiasi computer presente nella rete in cui è stato distribuito Skype for Business Server.
    
2. Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il pannello di controllo di Skype for Business Server. 
    
3. Sulla barra di spostamento sinistra fare clic su **Sicurezza** e quindi su **Criteri PIN**.
    
4. Nella pagina **Criteri PIN** fare clic su **Nuovo** e quindi eseguire una delle operazioni seguenti:
    
   - Per creare criteri a livello di utente fare clic su **Criteri utente**. In **Crea nuovi criteri PIN** digitare un nome descrittivo dei criteri in **Nome**.
    
   - Per creare criteri a livello di sito, fare clic su **Criteri sito**. Nel campo di ricerca **Seleziona un sito** digitare il nome del sito per cui si desidera creare i criteri, per intero o in parte. Fare clic sul sito desiderato nell'elenco dei siti risultante e quindi fare clic su **OK**.
    
5. Nel campo **Descrizione** digitare una descrizione per i criteri PIN.
    
6. Nel campo **Lunghezza minima PIN** digitare o selezionare la lunghezza minima che si desidera consentire per il PIN. La lunghezza minima predefinita è di cinque cifre.
    
7. Per poter specificare il numero massimo di tentativi di accesso prima che un utente venga bloccato, selezionare la casella di controllo **Specifica numero massimo di tentativi di accesso**. Se non si seleziona questa opzione, il numero massimo di tentativi consentiti viene determinato automaticamente in base alla lunghezza del PIN. Per impostazione predefinita, il numero massimo di tentativi viene determinato automaticamente.
    
8. Se si seleziona la casella di controllo **Specifica numero massimo di tentativi di accesso**, in **Numero massimo di tentativi di accesso** digitare o selezionare il numero massimo di tentativi di accesso che si desidera consentire.
    
9. Per impostare una scadenza per i PIN, selezionare la casella di controllo **Abilita scadenza PIN**. Se non si seleziona questa opzione, i PIN non scadranno mai, come da impostazione predefinita.
    
10. Se si seleziona la casella di controllo **Abilita scadenza PIN**, in **Scadenza PIN dopo (giorni)** digitare o selezionare il numero di giorni trascorsi i quali scadranno i PIN.
    
11. In **Conteggio cronologia PIN** digitare il numero di PIN che deve creare un utente prima che possa riutilizzare un PIN. Per impostazione predefinita, gli utenti possono riutilizzare i loro PIN.
    
12. Per consentire modelli comuni di cifre nei pin, ad esempio "1234" e "8888", selezionare la casella di controllo **Consenti modelli comuni** . Se non si seleziona questa opzione, saranno consentiti solo formati complessi di cifre. Per impostazione predefinita, sono consentiti solo formati complessi di cifre.
    
    > [!IMPORTANT]
    > È consigliabile evitare di consentire i formati comuni. 
  
13. Fare clic su **Commit**.
    

