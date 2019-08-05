---
title: Configurare la connettività ibrida | Distribuire Skype for Business Server 2019 Connect
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: bjwhalen
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
description: Istruzioni per l'implementazione della connettività ibrida tra Skype for Business Server e Skype for business online.
ms.openlocfilehash: ab7fb32c16e57e554c702a7b0f29ba350c1eedbe
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36185459"
---
# <a name="configure-hybrid-connectivity-between-skype-for-business-server-and-office-365"></a>Configurare la connettività ibrida tra Skype for Business Server e Office 365

**Riepilogo:** Leggere questo argomento per informazioni su come configurare la connettività ibrida tra Skype for Business Server e teams o Skype for business online.  La connettività ibrida consente di trasferire gli utenti locali in teams o Skype for business online e consente agli utenti di usufruire dei servizi cloud.
  
Prima di eseguire la procedura descritta in questo argomento, è necessario disporre di una [connessione ibrida per la lettura del piano tra Skype for Business Server e Office 365](plan-hybrid-connectivity.md).
  
La tabella seguente elenca le attività necessarie per configurare la connettività ibrida di Skype for business e fornisce collegamenti agli articoli associati per altre informazioni.
  
|Passaggio|Descrizione|
|:-----|:-----|
|Creare un account del tenant per Office 365   <br/> |Informazioni su Office 365 in [office 365](https://go.microsoft.com/fwlink/p/?LinkId=254980).  <br/> Per verificare che l'ambiente sia pronto per Office 365, vedere requisiti di [sistema](https://products.office.com/en-US/office-system-requirements).  <br/> Per informazioni dettagliate sulla configurazione di Office 365, vedere [Introduzione a office 365](https://go.microsoft.com/fwlink/p/?LinkId=254982).  <br/> |
|Aggiungere il dominio al tenant di Office 365 e verificare la proprietà  <br/> | È necessario aggiungere il dominio al tenant di Office 365 e seguire la procedura per convalidare il dominio con Office 365. Questo per verificare di essere il proprietario del dominio. <br/> Per aggiungere il dominio al tenant di Office 365, seguire la procedura descritta in [aggiungere un dominio a office 365](https://support.office.com/en-us/article/add-a-domain-to-office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611?ui=en-US&rs=en-US&ad=US).  <br/> |
|Configurare la sincronizzazione di Active Directory  <br/> |La sincronizzazione di Active Directory consente di mantenere costantemente sincronizzata la Active Directory locale con Office 365. In questo modo è possibile creare versioni sincronizzate di ogni account utente e gruppo.  <br/> <br> **Importante:** È necessario sincronizzare gli account degli annunci per tutti gli utenti di Skype for business nell'organizzazione tra le distribuzioni locali e online, anche se gli utenti non vengono spostati in teams o in Skype for business online. Se non si sincronizzano tutti gli utenti, la comunicazione tra gli utenti locali e online dell'organizzazione potrebbe non funzionare come previsto. Per altre informazioni, vedere [configurare Azure ad Connect per ambienti ibridi](configure-azure-ad-connect.md).         |
| Configurare Skype for business Hybrid | Sono disponibili tre passaggi di base: <br><br> 1. configurare l'ambiente locale per la Federazione con Office 365. <br> 2. configurare l'ambiente locale per considerare attendibile Office 365 e abilitare lo spazio di indirizzi SIP condiviso con Office 365.<br> 3. abilitare lo spazio di indirizzi SIP condiviso nel tenant di Office 365. <br><br> Inoltre, se si dispone di Exchange locale, è consigliabile configurare OAuth tra gli ambienti Exchange locale e Skype for business online. <br> <br>Per altre informazioni, vedere [Configurare Skype for business Hybrid](configure-federation-with-skype-for-business-online.md).
|Trasferire utenti pilota  <br/> |Dopo aver completato la procedura per preparare e configurare l'ambiente per i team o Skype for business online, è possibile iniziare a spostare gli utenti pilota nel tenant online di Office 365. Per altre informazioni, vedere [trasferire utenti da locali a Skype for business online](move-users-from-on-premises-to-skype-for-business-online.md) e [trasferire utenti da locale a teams](move-users-from-on-premises-to-Teams.md).  <br/> |