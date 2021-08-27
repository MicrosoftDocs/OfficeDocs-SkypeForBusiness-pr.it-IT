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
ms.localizationpriority: medium
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
description: Istruzioni per l'implementazione della connettività ibrida tra Skype for Business Server e Teams.
ms.openlocfilehash: 67caabe77afb9f06dcf28f47a93f8eef06c08de8
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/26/2021
ms.locfileid: "58624568"
---
# <a name="configure-hybrid-connectivity-between-skype-for-business-server-and-teams"></a>Configurare la connettività ibrida tra Skype for Business Server e Teams

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

**Riepilogo:** Leggere questo argomento per informazioni su come configurare la connettività ibrida tra Skype for Business Server e Teams.  La connettività ibrida consente di spostare gli utenti locali in Teams e consente agli utenti di sfruttare i servizi cloud.
  
Prima di eseguire i passaggi descritti in questo argomento, è necessario leggere Plan [hybrid connectivity between Skype for Business Server and Teams](plan-hybrid-connectivity.md).
  
Nella tabella seguente sono elencate le attività necessarie per configurare la Skype for Business ibrida e vengono forniti collegamenti agli articoli associati per ulteriori informazioni.
  
|Passaggio|Descrizione|
|:-----|:-----|
|Creare un account tenant per Microsoft 365   <br/> |Per informazioni Microsoft 365 su [Microsoft 365](https://go.microsoft.com/fwlink/p/?LinkId=254980).  <br/> Per verificare che l'ambiente sia pronto per Microsoft 365, vedere Requisiti [di sistema](https://products.office.com/office-system-requirements).  <br/> Per informazioni dettagliate sulla configurazione Microsoft 365, vedere [Introduzione a Microsoft 365](https://go.microsoft.com/fwlink/p/?LinkId=254982).  <br/> |
|Aggiungere il dominio all'organizzazione Microsoft 365 e verificare la proprietà  <br/> | È necessario aggiungere il dominio all'organizzazione Microsoft 365 e quindi seguire la procedura per convalidare il dominio con Microsoft 365. Questo per confermare di essere il proprietario del dominio. <br/> Per aggiungere il dominio all'organizzazione Microsoft 365, seguire la procedura descritta in [Aggiungere un dominio a Microsoft 365](https://support.office.com/article/add-a-domain-to-office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611?ui=en-US&rs=en-US&ad=US).  <br/> |
|Configurare la sincronizzazione di Active Directory  <br/> |La sincronizzazione di Active Directory mantiene l'Active Directory locale costantemente sincronizzato con Microsoft 365. In questo modo è possibile creare versioni sincronizzate di ogni account utente e gruppo.  <br/> <br> **Importante:** È necessario sincronizzare gli account AD per tutti gli utenti Skype for Business dell'organizzazione tra le distribuzioni locali e online, anche se gli utenti non vengono spostati in Teams. Se non si sincronizzano tutti gli utenti, le comunicazioni tra utenti locali e online nell'organizzazione potrebbero non funzionare come previsto. Per ulteriori informazioni, vedere [Configure Azure AD Connessione for hybrid environments](configure-azure-ad-connect.md).         |
| Configurare Skype for Business ibrido | Questa procedura prevede tre passaggi di base: <br><br> 1. Configurare l'ambiente locale per la federazione con Microsoft 365. <br> 2. Configurare l'ambiente locale in modo che ritieni attendibile Microsoft 365 e abilitare lo spazio di indirizzi SIP condiviso con Microsoft 365.<br> 3. Abilitare lo spazio di indirizzi SIP condiviso nell'Microsoft 365 organizzazione. <br><br> Inoltre, se si dispone Exchange locale, è possibile configurare OAuth tra l'Exchange locale e gli ambienti online. <br> <br>Per ulteriori informazioni, vedere [Configure Skype for Business hybrid](configure-federation-with-skype-for-business-online.md).
|Spostare utenti pilota  <br/> |Dopo aver completato i passaggi per preparare e configurare l'ambiente per Teams, è possibile iniziare a spostare gli utenti pilota nell'organizzazione Microsoft 365 online. Per ulteriori informazioni, vedere [Move users from on premises to Teams](move-users-from-on-premises-to-Teams.md).  <br/> |
