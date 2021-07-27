---
title: Configurare la connettività ibrida | Distribuire Skype for Business Server 2019 connect
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
description: Istruzioni per l'implementazione della connettività ibrida tra Skype for Business Server e Teams.
ms.openlocfilehash: 2b0e9aabbe029dd292afabf3b7cac579f1029384
ms.sourcegitcommit: 9879bc587382755d9a5cd63a75b0e7dc4e15574c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/21/2021
ms.locfileid: "53510547"
---
# <a name="configure-hybrid-connectivity-between-skype-for-business-server-and-teams"></a>Configurare la connettività ibrida tra Skype for Business Server e Teams

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

**Riepilogo:** Leggere questo argomento per informazioni su come configurare la connettività ibrida tra Skype for Business Server e Teams (o Skype for Business Online fino al suo ritiro).  La connettività ibrida consente di spostare gli utenti locali in Teams (o Skype for Business Online) e consente agli utenti di sfruttare i servizi cloud.
  
Prima di eseguire i passaggi descritti in questo argomento, è necessario leggere [Plan hybrid connectivity between Skype for Business Server and Teams](plan-hybrid-connectivity.md).
  
Nella tabella seguente sono elencate le attività necessarie per configurare la Skype for Business ibrida e vengono forniti collegamenti agli articoli associati per ulteriori informazioni.
  
|Passaggio|Descrizione|
|:-----|:-----|
|Creare un account tenant per Microsoft 365   <br/> |Per informazioni Microsoft 365 su [Microsoft 365](https://go.microsoft.com/fwlink/p/?LinkId=254980).  <br/> Per verificare che l'ambiente sia pronto per Microsoft 365, vedere Requisiti [di sistema](https://products.office.com/office-system-requirements).  <br/> Per informazioni dettagliate sulla configurazione Microsoft 365, vedere [Getting Started with Microsoft 365](https://go.microsoft.com/fwlink/p/?LinkId=254982).  <br/> |
|Aggiungere il dominio all'organizzazione Microsoft 365 e verificare la proprietà  <br/> | È necessario aggiungere il dominio all'organizzazione Microsoft 365 e quindi seguire la procedura per convalidare il dominio con Microsoft 365. Questo per confermare di essere il proprietario del dominio. <br/> Per aggiungere il dominio all'organizzazione Microsoft 365, seguire la procedura descritta in [Aggiungere un dominio a Microsoft 365](https://support.office.com/article/add-a-domain-to-office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611?ui=en-US&rs=en-US&ad=US).  <br/> |
|Configurare la sincronizzazione di Active Directory  <br/> |La sincronizzazione di Active Directory mantiene l'Active Directory locale costantemente sincronizzato con Microsoft 365. In questo modo è possibile creare versioni sincronizzate di ogni account utente e gruppo.  <br/> <br> **Importante:** È necessario sincronizzare gli account AD per tutti gli utenti Skype for Business dell'organizzazione tra le distribuzioni locali e online, anche se gli utenti non vengono spostati in Teams (o Skype for Business Online). Se non si sincronizzano tutti gli utenti, le comunicazioni tra utenti locali e online nell'organizzazione potrebbero non funzionare come previsto. Per ulteriori informazioni, vedere [Configure Azure AD Connessione for hybrid environments](configure-azure-ad-connect.md).         |
| Configurare Skype for Business ibrido | Questa procedura prevede tre passaggi di base: <br><br> 1. Configurare l'ambiente locale per la federazione con Microsoft 365. <br> 2. Configurare l'ambiente locale in modo che ritieni attendibile Microsoft 365 e abilitare lo spazio di indirizzi SIP condiviso con Microsoft 365.<br> 3. Abilitare lo spazio di indirizzi SIP condiviso nell'Microsoft 365 organizzazione. <br><br> Inoltre, se si dispone di Exchange locale, è consigliabile configurare OAuth tra gli ambienti Exchange locali e Skype for Business Online. <br> <br>Per ulteriori informazioni, vedere [Configure Skype for Business hybrid](configure-federation-with-skype-for-business-online.md).
|Spostare utenti pilota  <br/> |Dopo aver completato i passaggi per preparare e configurare l'ambiente per Teams (o Skype for Business Online), è possibile iniziare a spostare gli utenti pilota nell'organizzazione Microsoft 365 online. Per ulteriori informazioni, vedere [Move users from on premises to Teams](move-users-from-on-premises-to-Teams.md) and Move users from on [premises to Skype for Business Online.](move-users-from-on-premises-to-skype-for-business-online.md)  <br/> |
