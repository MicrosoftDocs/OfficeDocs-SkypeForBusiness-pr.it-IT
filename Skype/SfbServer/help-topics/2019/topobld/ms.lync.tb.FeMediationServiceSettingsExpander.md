---
title: Espansione delle impostazioni del servizio Mediation
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
  - CSH
ms.custom:
  - ms.lync.tb.FeMediationServiceSettingsExpander
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 142c1acd-cdaa-4922-8379-aa1bdf56a964
ROBOTS: 'NOINDEX, NOFOLLOW'
description: 'Per Mediation Server è possibile specificare quanto segue:'
---

# <a name="mediation-service-settings-expander"></a>Espansione delle impostazioni del servizio Mediation

Per **Mediation Server** è possibile specificare quanto segue:

Se si colloca il Mediation Server nel pool Front End o nel server edizione Standard, selezionare la casella di controllo **Mediation Server collocato abilitato**. Se si sceglie di non collocare il Mediation Server, non vi sono impostazioni che è possibile definire in questa sezione.

Se il collocamento di Mediation Server è stato abilitato, sarà necessario definire l'intervallo delle porte di attesa sul server per TLS (Transport Layer Security). Per impostazione predefinita, questa porta è la 5067. Se si seleziona **Abilita porta TCP**, sarà necessario definire una porta TCP (Transmission Control Protocol) per il Mediation Server collocato. Questa è un'impostazione facoltativa e, per determinare se sia necessaria, è consigliabile fare riferimento ai requisiti del gateway o della rete PSTN (Public Switched Telephone Network). Per impostazione predefinita, il valore della porta TCP è 5068.

Definire gateway PSTN associati al Mediation Server collocato. Se i gateway sono già stati definiti, saranno disponibili per l'associazione al Mediation Server.

Se a un Mediation Server è associato più di un gateway, il primo gateway associato sarà quello predefinito. Se è necessario scegliere un altro gateway come predefinito, selezionare il gateway desiderato e fare clic su **Rendi predefinito**. Per annullare la selezione di un gateway come predefinito, fare clic su **Annulla predefinito**.

Per informazioni dettagliate sulla definizione e la configurazione delle impostazioni per il pool Front End edizione Enterprise o il server edizione Standard, vedere [Defining and Configuring the Topology](/previous-versions/office/lync-server-2013/lync-server-2013-defining-and-configuring-the-topology) e [Deploying Mediation Server e Defining Peers](/previous-versions/office/lync-server-2013/lync-server-2013-deploying-mediation-servers-and-defining-peers).