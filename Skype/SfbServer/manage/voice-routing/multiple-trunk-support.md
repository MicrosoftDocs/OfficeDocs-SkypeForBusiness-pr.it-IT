---
title: Supporto di più trunk in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: Skype for Business Server supporta più associazioni tra gateway e Mediation Server. Queste associazioni vengono effettuate definendo un trunk, ovvero un'associazione logica tra un pool Mediation Server e un gateway PSTN (Public Switched Telephone Network), session border controller (SBC) o IP-PBX. Utilizzare il Generatore di topologie per associare i gateway ai Mediation Server, ovvero i trunk.
ms.openlocfilehash: 0e4bc7d0248fa9116651a1384a17a7a8347b2d8f
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/30/2021
ms.locfileid: "58729045"
---
# <a name="multiple-trunk-support-in-skype-for-business-server"></a>Supporto di più trunk in Skype for Business Server

Skype for Business Server supporta più associazioni tra gateway e Mediation Server. Queste associazioni vengono effettuate definendo un trunk, ovvero un'associazione logica tra un pool Mediation Server e un gateway PSTN (Public Switched Telephone Network), session border controller (SBC) o IP-PBX. Utilizzare il Generatore di topologie per associare i gateway ai Mediation Server, ovvero i trunk.

- Per assegnare o rimuovere un trunk in Skype for Business Server, è innanzitutto necessario definire un trunk in Generatore di topologie. Un trunk è costituito dalla seguente associazione: nome di dominio completo (FQDN) di Mediation Server, porta di attesa mediation server, FQDN gateway e porta di attesa del gateway.
- Per configurare più trunk, è possibile creare più associazioni tra lo stesso gateway e il Mediation Server. Ciò garantisce ulteriore resilienza all'infrastruttura VoIP aziendale, particolarmente utile in scenari di interoperabilità PBX (Private Branch Exchange). 

Dopo essere stato definito, il trunk deve essere associato a una route. Per associare un trunk a una route, è necessario definire un nome semplice per il trunk in Generatore di topologie. Questo nome semplice viene utilizzato come nome trunk nel Skype for Business Server Pannello di controllo, dove i trunk possono essere associati alle route. Il nome del trunk semplice viene utilizzato come nome del gateway da Skype for Business Server Management Shell.

`New-CsVoiceRoute -Identity <RouteId> -NumberPattern <String> -PstnUsages @{add="<UsageString>"} -PstnGatewayList @{add="<TrunkSimpleName>"}`

L'amministratore deve selezionare un trunk predefinito associato a un Mediation Server. In Generatore di topologie fare clic con il pulsante destro del mouse sul Mediation Server associato e quindi scegliere **Proprietà**. Specificare il gateway predefinito per il Mediation Server. 

Nel diagramma seguente vengono illustrati i più trunk definiti per ogni Mediation Server e gateway. 

![Assegnazioni di più trunk.](../../media/multiple-trunk-assignments.jpg)
