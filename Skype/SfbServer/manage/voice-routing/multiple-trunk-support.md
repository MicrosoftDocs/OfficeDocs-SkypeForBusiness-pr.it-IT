---
title: Supporto per più trunk in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: La funzionalità di Skype for Business Server supporta più associazioni tra gateway e Mediation Server. Queste associazioni vengono eseguite definendo un trunk, che è un'associazione logica tra un pool di Mediation Server e un gateway PSTN (Public Switched Telephone Network), Session Border Controller (SBC) o IP-PBX. Utilizzare il generatore di topologie per associare i gateway a Mediation Server (ovvero Trunks).
ms.openlocfilehash: 0f4c8d2ee16c900ef666c12230964a9abb8f5a48
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49826226"
---
# <a name="multiple-trunk-support-in-skype-for-business-server"></a>Supporto per più trunk in Skype for Business Server

La funzionalità di Skype for Business Server supporta più associazioni tra gateway e Mediation Server. Queste associazioni vengono eseguite definendo un trunk, che è un'associazione logica tra un pool di Mediation Server e un gateway PSTN (Public Switched Telephone Network), Session Border Controller (SBC) o IP-PBX. Utilizzare il generatore di topologie per associare i gateway a Mediation Server (ovvero Trunks).

- Per assegnare o rimuovere un trunk in Skype for Business Server, è innanzitutto necessario definire un trunk in Generatore di topologie. Un trunk è costituito dai seguenti elementi: Mediation Server Fully Qualified Domain Name (FQDN), la porta di attesa Mediation Server, il nome di dominio completo del gateway e la porta di attesa del gateway.
- Per configurare più trunk, è possibile creare più associazioni tra lo stesso gateway e il Mediation Server. Questo fornisce ulteriore resilienza all'infrastruttura VoIP aziendale, che è particolarmente utile in scenari di interoperabilità PBX (Private Branch Exchange). 

Dopo essere stato definito, il trunk deve essere associato a una route. Per associare un trunk a una route, è possibile definire un nome semplice per il trunk in Generatore di topologie. Questo nome semplice viene utilizzato come nome del trunk nel pannello di controllo di Skype for Business Server, dove Trunks può essere associato a route. Il nome del trunk semplice viene utilizzato come nome del gateway da Skype for Business Server Management Shell.

`New-CsVoiceRoute -Identity <RouteId> -NumberPattern <String> -PstnUsages @{add="<UsageString>"} -PstnGatewayList @{add="<TrunkSimpleName>"}`

L'amministratore deve selezionare un trunk predefinito associato a un Mediation Server. Dal generatore di topologie fare clic con il pulsante destro del mouse sul Mediation Server associato e quindi scegliere **Proprietà**. Specificare il gateway predefinito per il Mediation Server. 

Nel diagramma seguente vengono illustrati i trunk multipli definiti per ogni Mediation Server e gateway. 

![Assegnazioni di più trunk](../../media/multiple-trunk-assignments.jpg)
