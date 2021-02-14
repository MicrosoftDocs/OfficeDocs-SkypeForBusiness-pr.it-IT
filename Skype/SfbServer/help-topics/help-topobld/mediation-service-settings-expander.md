---
title: Espansione delle impostazioni del servizio Mediation
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/26/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.FeMediationServiceSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 142c1acd-cdaa-4922-8379-aa1bdf56a964
description: 'Per Mediation Server è possibile specificare quanto segue:'
ms.openlocfilehash: 0e6e9101b8b0a530b0f47411f1d8ce1eaa2e01b5
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49810276"
---
# <a name="mediation-service-settings-expander"></a>Espansione delle impostazioni del servizio Mediation

Per **Mediation Server** è possibile specificare quanto segue:

Se si colloca il Mediation Server nel pool Front End o nel server Standard Edition, selezionare la casella di controllo **Mediation Server collocato abilitato.** Se si sceglie di non collocare il Mediation Server, non vi sono impostazioni che è possibile definire in questa sezione.

Se il collocamento di Mediation Server è stato abilitato, sarà necessario definire l'intervallo delle porte di attesa sul server per TLS (Transport Layer Security). Per impostazione predefinita, questa porta è la 5067. Se si seleziona **Abilita porta TCP**, sarà necessario definire una porta TCP (Transmission Control Protocol) per il Mediation Server collocato. Questa è un'impostazione facoltativa e, per determinare se sia necessaria, è consigliabile fare riferimento ai requisiti del gateway o della rete PSTN (Public Switched Telephone Network). Per impostazione predefinita, il valore della porta TCP è 5068.

Definire gateway PSTN associati al Mediation Server collocato. Se i gateway sono già stati definiti, saranno disponibili per l'associazione al Mediation Server.

Se a un Mediation Server è associato più di un gateway, il primo gateway associato sarà quello predefinito. Se è necessario scegliere un altro gateway come predefinito, selezionare il gateway desiderato e fare clic su **Rendi predefinito**. Per annullare la selezione di un gateway come predefinito, fare clic su **Annulla predefinito**.

Per informazioni dettagliate sulla definizione e la configurazione delle impostazioni per il pool Enterprise Edition Front End o il server Standard Edition, vedere [Defining and Configuring the Topology](https://technet.microsoft.com/library/51d1601e-4f83-48d4-ad08-3b4d5e2003aa.aspx) and [Deploying Mediation Servers and Defining Peers.](https://technet.microsoft.com/library/a684f1da-6671-4011-adf6-2db49e2528e2.aspx)


