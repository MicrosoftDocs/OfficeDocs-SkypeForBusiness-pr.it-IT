---
title: Supporto per più trunk in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: La funzionalità di Skype for Business Server supporta più associazioni tra gateway e Mediation Server. Queste associazioni vengono effettuate definendo un trunk, che è un'associazione logica tra un pool di Mediation Server e un gateway PSTN (Public Switched Telephone Network), Session Border Controller (SBC) o IP-PBX. Usare il generatore di topologie per associare i gateway ai server di mediazione (ovvero Trunks).
ms.openlocfilehash: 6f950f089d23687f0215bd9db1f253eb57c17c75
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816946"
---
# <a name="multiple-trunk-support-in-skype-for-business-server"></a>Supporto per più trunk in Skype for Business Server

La funzionalità di Skype for Business Server supporta più associazioni tra gateway e Mediation Server. Queste associazioni vengono effettuate definendo un trunk, che è un'associazione logica tra un pool di Mediation Server e un gateway PSTN (Public Switched Telephone Network), Session Border Controller (SBC) o IP-PBX. Usare il generatore di topologie per associare i gateway ai server di mediazione (ovvero Trunks).

- Per assegnare o rimuovere un trunk in Skype for Business Server, è necessario prima di tutto definire un trunk in Generatore di topologie. Un trunk è costituito dall'associazione seguente: Mediation Server Fully Qualified Domain Name (FQDN), la porta di ascolto di Mediation Server, il nome di dominio completo del gateway e la porta di ascolto del gateway.
- Per configurare più Trunks, è possibile creare più associazioni tra lo stesso gateway e il Mediation Server. In questo modo è disponibile un'ulteriore resilienza dell'infrastruttura VoIP aziendale, che risulta particolarmente utile negli scenari di interoperabilità del PBX (Private Branch Exchange). 

Quando viene definito un trunk, deve essere associato a una route. Per associare un trunk a una route, è possibile definire un nome semplice per il trunk in Generatore di topologia. Questo nome semplice viene usato come nome del trunk nel pannello di controllo di Skype for Business Server, dove Trunks può essere associato alle route. Il nome del trunk semplice viene usato come nome del gateway da Skype for Business Server Management Shell.

`New-CsVoiceRoute -Identity <RouteId> -NumberPattern <String> -PstnUsages @{add="<UsageString>"} -PstnGatewayList @{add="<TrunkSimpleName>"}`

L'amministratore deve selezionare un trunk predefinito associato a un Mediation Server. In Generatore di topologie fare clic con il pulsante destro del mouse sul server di mediazione associato e quindi scegliere **Proprietà**. Specificare il gateway predefinito per il Mediation Server. 

Il diagramma seguente illustra i trunk più definiti per ogni Mediation Server e gateway. 

![Più assegnazioni trunk](../../media/multiple-trunk-assignments.jpg)
