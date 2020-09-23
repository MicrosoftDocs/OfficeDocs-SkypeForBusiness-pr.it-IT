---
title: Espansione delle impostazioni del servizio Mediation
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
ms.openlocfilehash: 9a6da594452b4675b3eed1ca734fa3b54c9117b9
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/23/2020
ms.locfileid: "48215147"
---
# <a name="mediation-service-settings-expander"></a>Espansione delle impostazioni del servizio Mediation

Per **Mediation Server** è possibile specificare quanto segue:

Se si sta collocando il Mediation Server nel pool Front end o nel server Standard Edition, selezionare la casella di controllo **Mediation Server collocato abilitato**. Se si sceglie di non collocare il Mediation Server, non vi sono impostazioni che è possibile definire in questa sezione.

Se il collocamento di Mediation Server è stato abilitato, sarà necessario definire l'intervallo delle porte di attesa sul server per TLS (Transport Layer Security). Per impostazione predefinita, questa porta è la 5067. Se si seleziona **Abilita porta TCP**, sarà necessario definire una porta TCP (Transmission Control Protocol) per il Mediation Server collocato. Questa è un'impostazione facoltativa e, per determinare se sia necessaria, è consigliabile fare riferimento ai requisiti del gateway o della rete PSTN (Public Switched Telephone Network). Per impostazione predefinita, il valore della porta TCP è 5068.

Definire gateway PSTN associati al Mediation Server collocato. Se i gateway sono già stati definiti, saranno disponibili per l'associazione al Mediation Server.

Se a un Mediation Server è associato più di un gateway, il primo gateway associato sarà quello predefinito. Se è necessario scegliere un altro gateway come predefinito, selezionare il gateway desiderato e fare clic su **Rendi predefinito**. Per annullare la selezione di un gateway come predefinito, fare clic su **Annulla predefinito**.

Per informazioni dettagliate sulla definizione e sulla configurazione delle impostazioni per il pool Enterprise Edition front end o il server Standard Edition, vedere [definizione e configurazione della topologia](https://technet.microsoft.com/library/51d1601e-4f83-48d4-ad08-3b4d5e2003aa.aspx) e [distribuzione di Mediation Server e definizione di peer](https://technet.microsoft.com/library/a684f1da-6671-4011-adf6-2db49e2528e2.aspx).


