---
title: Impedire le sessioni per i servizi
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: È possibile usare il pannello di controllo installazioni legacy per impedire la nuova sessione per tutti i servizi legacy in uso in un computer specifico o per impedire la nuova sessione di un servizio legacy specifico.
ms.openlocfilehash: 5bba30bee0fb8c25bed25e2c3cbd593179aa9b97
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41813054"
---
# <a name="prevent-sessions-for-services"></a>Impedire le sessioni per i servizi

È possibile usare il pannello di controllo installazioni legacy per impedire la nuova sessione per tutti i servizi legacy in uso in un computer specifico o per impedire la nuova sessione di un servizio legacy specifico.
  
## <a name="to-prevent-new-sessions-for-services-on-a-computer"></a>Per evitare nuove sessioni per i servizi in un computer

1. Da un account utente che è un membro del gruppo RTCUniversalServerAdmins (o ha diritti utente equivalenti) o assegnato al ruolo CsServerAdministrator o CsAdministrator, accedere a qualsiasi computer presente nella rete in cui è stato distribuito Skype for Business Server. 2019.
    
2. Aprire il pannello di controllo di Skype for business.
    
3. Nella barra di spostamento sinistra fare clic su **topologia**e quindi su **stato**.
    
4. Nella pagina **stato** ordinare o cercare l'elenco in base alle esigenze per trovare il computer in cui sono in esecuzione i servizi per cui si vogliono impedire le nuove sessioni e quindi fare clic su di esso. 
    
5. Fare clic su **azione**.
    
6. Fare clic su **Impedisci nuove sessioni per tutti i servizi**.
    
## <a name="to-prevent-new-sessions-for-a-specific-service"></a>Per impedire nuove sessioni per un servizio specifico

1. Da un account utente che è un membro del gruppo RTCUniversalServerAdmins (o ha diritti utente equivalenti) o assegnato al ruolo CsServerAdministrator o CsAdministrator, accedere a qualsiasi computer presente nella rete in cui è stato distribuito Skype for Business Server. 2019.
    
2. Aprire il pannello di controllo di Skype for business.
    
3. Nella barra di spostamento sinistra fare clic su **topologia**e quindi su **stato**.
    
4. Nella pagina **stato** ordinare o cercare l'elenco in base alle esigenze per trovare il computer in cui è in esecuzione il servizio che si vuole avviare o arrestare e quindi fare clic su di esso. 
    
5. Fare clic su **Proprietà**.
    
6. Ordinare l'elenco dei servizi, se necessario, e fare clic sul servizio per cui si vogliono impedire le nuove sessioni.
    
7. Fare clic su **azione**.
    
8. Fare clic su **Impedisci nuove sessioni per il servizio**.
    
9. Fare clic su **Chiudi**.
    

