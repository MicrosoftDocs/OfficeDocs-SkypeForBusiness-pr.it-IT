---
title: Configurare la connettività ibrida | Distribuire Skype for Business Server 2019 Connect
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: bjwhalen
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
description: Istruzioni per l'implementazione della connettività ibrida tra Skype for Business Server e Skype for Business online.
ms.openlocfilehash: 3a68d39062387952b7a43bb22599265a69bf7a61
ms.sourcegitcommit: 80b66127b3415c99f9468625add6a8f2c36bca74
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/07/2020
ms.locfileid: "48376749"
---
# <a name="configure-hybrid-connectivity-between-skype-for-business-server-and-office-365"></a>Configurare la connettività ibrida tra Skype for Business Server e Office 365

**Riepilogo:** Leggere questo argomento per informazioni su come configurare la connettività ibrida tra Skype for Business Server e Teams o Skype for Business online.  La connettività ibrida consente di spostare gli utenti locali in Teams o Skype for Business online e consente agli utenti di sfruttare i servizi cloud.
  
Prima di eseguire i passaggi descritti in questo argomento, è consigliabile leggere Pianificare la connettività ibrida [tra Skype for Business Server e Office 365.](plan-hybrid-connectivity.md)
  
Nella tabella seguente sono elencate le attività necessarie per configurare la connettività ibrida di Skype for Business e vengono forniti collegamenti agli articoli associati per ulteriori informazioni.
  
|Passaggio|Descrizione|
|:-----|:-----|
|Creare un account tenant per Office 365   <br/> |Informazioni su Office 365 [in Office 365.](https://go.microsoft.com/fwlink/p/?LinkId=254980)  <br/> Per verificare che l'ambiente sia pronto per Office 365, vedere i [requisiti di sistema.](https://products.office.com/office-system-requirements)  <br/> Per informazioni dettagliate sulla configurazione di Office 365, vedere [Introduzione a Office 365.](https://go.microsoft.com/fwlink/p/?LinkId=254982)  <br/> |
|Aggiungere il dominio all'organizzazione di Office 365 e verificare la proprietà  <br/> | È necessario aggiungere il dominio all'organizzazione di Office 365 e quindi seguire la procedura per convalidare il dominio con Office 365. Ciò consente di confermare di essere il proprietario del dominio. <br/> Per aggiungere il dominio all'organizzazione di Office 365, seguire la procedura descritta in Aggiungere un dominio [a Office 365.](https://support.office.com/article/add-a-domain-to-office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611?ui=en-US&rs=en-US&ad=US)  <br/> |
|Configurare la sincronizzazione di Active Directory  <br/> |La sincronizzazione di Active Directory mantiene Active Directory locale continuamente sincronizzato con Office 365. In questo modo è possibile creare versioni sincronizzate di ogni account utente e gruppo.  <br/> <br> **Importante:** È necessario sincronizzare gli account AD per tutti gli utenti di Skype for Business nell'organizzazione tra le distribuzioni locali e online, anche se gli utenti non vengono spostati in Teams o Skype for Business online. Se non si sincronizzano tutti gli utenti, le comunicazioni tra gli utenti locali e online nell'organizzazione potrebbero non funzionare come previsto. Per ulteriori informazioni, vedere [Configurare Azure AD Connect per ambienti ibridi.](configure-azure-ad-connect.md)         |
| Configurare Skype for Business ibrido | Questa procedura prevede tre passaggi di base: <br><br> 1. Configurare l'ambiente locale per la federazione con Office 365. <br> 2. Configurare l'ambiente locale per considerare attendibile Office 365 e abilitare lo spazio di indirizzi SIP condiviso con Office 365.<br> 3. Abilitare lo spazio di indirizzi SIP condiviso nell'organizzazione di Office 365. <br><br> Inoltre, se si dispone di Exchange locale, è consigliabile configurare OAuth tra gli ambienti Exchange locali e Skype for Business Online. <br> <br>Per ulteriori informazioni, vedere [Configurare Skype for Business ibrido.](configure-federation-with-skype-for-business-online.md)
|Spostare utenti pilota  <br/> |Dopo aver completato i passaggi per preparare e configurare l'ambiente per Teams o Skype for Business online, è possibile iniziare a spostare gli utenti pilota nell'organizzazione di Office 365 online. Per altre informazioni, vedere Spostare gli utenti dall'ambiente locale [a Skype for Business online](move-users-from-on-premises-to-skype-for-business-online.md) e Spostare gli utenti [dall'ambiente locale a Teams.](move-users-from-on-premises-to-Teams.md)  <br/> |
