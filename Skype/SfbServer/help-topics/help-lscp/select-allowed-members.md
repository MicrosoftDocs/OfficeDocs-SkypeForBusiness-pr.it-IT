---
title: Selezionare i membri consentiti
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/24/2015
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.lscp.SelectAllowedMembers
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e9e6df4a-e58a-4104-9f72-2f5c818353e1
description: La creazione e la gestione di chat room persistenti è molto più semplice con l'uso corretto delle categorie. Un amministratore della chat persistente può definire AllowedMembers e creatori per ogni categoria e può anche definire le impostazioni e i comportamenti predefiniti della chat room che verranno applicati a tutte le chat room create nella categoria. Gli amministratori della chat persistente creano e gestiscono categorie usando il pannello di controllo o i cmdlet di Windows PowerShell.
ms.openlocfilehash: 916077fe25e1616888dd58dc40f0ef0f14c61e7a
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/03/2020
ms.locfileid: "41699701"
---
# <a name="select-allowed-members"></a>Selezionare i membri consentiti

La creazione e la gestione di chat room persistenti è molto più semplice con l'uso corretto delle categorie. Un amministratore della chat persistente può definire **AllowedMembers** e **creatori** per ogni categoria e può anche definire le impostazioni e i comportamenti predefiniti della chat room che verranno applicati a tutte le chat room create nella categoria. Gli amministratori della chat persistente creano e gestiscono categorie usando il pannello di controllo o i cmdlet di Windows PowerShell.

Gli utenti, le unità organizzative e i gruppi di utenti identificati come creatori della categoria sono gli unici autorizzati a creare chat room nella categoria. Dopo aver creato la categoria, possono scegliere utenti, unità organizzative e gruppi di utenti dall'elenco di **AllowedMembers** della categoria come Manager e membri della chat room per gestire e partecipare alla sala.

## <a name="tasks-that-you-can-perform"></a>Attività che è possibile eseguire

Nella pagina **Selezionare i membri consentiti** è possibile eseguire le attività seguenti:

- [Configure Categories](https://technet.microsoft.com/library/4547f514-f0c0-404d-890f-092ddeeac852.aspx)

- [New Persistent Chat Server Features](https://technet.microsoft.com/library/c3ec6f33-6261-4bf5-aa31-baa8ab2a87d8.aspx)

Per informazioni dettagliate sulle diverse procedure che è possibile eseguire tramite il pannello di controllo di Skype for Business Server, vedere [gestire Skype for Business server 2015](../../manage/manage.md).

## <a name="to-configure-categories-for-chat-rooms"></a>Per configurare le categorie delle chat room

In **appartenenza**, nella sezione **consentiti membri** , aggiungere o rimuovere utenti e altre entità di servizi di dominio Active Directory (utenti, gruppi di distribuzione, unità organizzative e così via) che possono essere aggiunti come membri delle chat room appartenenti alla categoria. Le entità consentite da una categoria possono cercare le chat della categoria (a meno che la chat non sia nascosta, caso in cui solo i membri della chat possono cercarla nella directory).


Per informazioni dettagliate sulle funzionalità e le funzionalità del server di chat persistente, vedere [Panoramica del server di chat persistente](https://technet.microsoft.com/library/23f7c886-304d-495a-ae70-3cbb44241acd.aspx) nella documentazione relativa alla pianificazione. Per informazioni dettagliate sull'uso delle configurazioni del server di chat persistente, vedere [configurazione del server di chat persistente](https://technet.microsoft.com/library/d90a4049-b268-4e8e-9f24-0cef08c8d9ed.aspx) nella documentazione di distribuzione e [gestione di Lync Server 2013, Persistent Chat Server](https://technet.microsoft.com/library/82befdc6-5d32-45f1-bfd7-aaedffed1ab8.aspx) nella documentazione Operations.

## <a name="see-also"></a>Vedere anche

[Understanding Persistent Chat Membership](https://technet.microsoft.com/library/900392d6-6e9f-4dae-93d6-39d7474409ef.aspx)
