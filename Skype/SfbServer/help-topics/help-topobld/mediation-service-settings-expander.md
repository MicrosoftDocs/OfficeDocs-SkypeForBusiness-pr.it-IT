---
title: Espansione delle impostazioni del servizio Mediation
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/26/2015
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.FeMediationServiceSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 142c1acd-cdaa-4922-8379-aa1bdf56a964
description: 'Per il Mediation Server è possibile specificare quanto segue:'
ms.openlocfilehash: fcff87faeb5911d12806f80499c2b2f0d63caff3
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36190130"
---
# <a name="mediation-service-settings-expander"></a>Espansione delle impostazioni del servizio Mediation

Per il **Mediation Server** è possibile specificare quanto segue:

Se si sta collocando il Mediation Server sul pool Front-end o sul server Standard Edition, selezionare la casella di controllo **Mediation Server collocato abilitato**. Se si sceglie di non collocare il Mediation Server, in questa sezione non sono disponibili impostazioni definibili.

Se è stata abilitata la collocazione di Mediation Server, è necessario definire l'intervallo della porta in attesa nel server per Transport Layer Security (TLS). Per impostazione predefinita, questa porta è la 5067. Se si seleziona **Abilita la porta TCP**, sarà necessario definire una porta TCP (Transmission Control Protocol) per il Mediation Server collocato. Questa è un'impostazione facoltativa e, per determinare se sia necessaria, è consigliabile fare riferimento ai requisiti del gateway o della rete PSTN (Public Switched Telephone Network). Per impostazione predefinita, il valore della porta TCP è 5068.

Puoi definire i gateway PSTN associati al Mediation Server collocato. Se sono già stati definiti gateway, saranno disponibili per l'associazione con il Mediation Server.

Se si ha più di un gateway associato a un Mediation Server, il primo gateway associato sarà il gateway predefinito. Se è necessario scegliere un altro gateway come predefinito, selezionare il gateway desiderato e fare clic su **Rendi predefinito**. Per annullare la selezione di un gateway come predefinito, fare clic su **Annulla predefinito**.

Per informazioni dettagliate su come definire e configurare le impostazioni per il pool di front end Enterprise Edition o per il server Standard Edition, vedere [definizione e configurazione della topologia](https://technet.microsoft.com/library/51d1601e-4f83-48d4-ad08-3b4d5e2003aa.aspx) e [distribuzione di Mediation Server e definizione di peer](https://technet.microsoft.com/library/a684f1da-6671-4011-adf6-2db49e2528e2.aspx).


