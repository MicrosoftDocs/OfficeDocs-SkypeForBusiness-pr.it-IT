---
title: Selezionare i membri consentiti
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/24/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.SelectAllowedMembers
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e9e6df4a-e58a-4104-9f72-2f5c818353e1
description: La creazione e la gestione delle chat room persistenti è molto più semplice con l'uso corretto delle categorie. Un amministratore di Persistent Chat può definire AllowedMembers e Creators per ogni categoria e può anche definire le impostazioni e i comportamenti predefiniti delle chat room che verranno applicati a tutte le chat room create nella categoria. Gli amministratori di Persistent Chat creano e gestiscono categorie utilizzando il pannello di controllo o Windows PowerShell cmdlet.
ms.openlocfilehash: 47abbec64f6799a85f3f6123a898eeae00becbdb
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51107992"
---
# <a name="select-allowed-members"></a>Selezionare membri consentiti

La creazione e la gestione delle chat room persistenti è molto più semplice con l'uso corretto delle categorie. Un amministratore di Persistent Chat può definire **AllowedMembers** e **Creators** per ogni categoria e può anche definire le impostazioni e i comportamenti predefiniti delle chat room che verranno applicati a tutte le chat room create nella categoria. Gli amministratori di Persistent Chat creano e gestiscono categorie utilizzando il pannello di controllo o Windows PowerShell cmdlet.

Utenti, unità organizzative e gruppi di utenti identificati come creatori della categoria sono gli unici individui e gruppi a cui è consentito creare chat nella categoria. Dopo aver creato la categoria, possono scegliere utenti, unità organizzative e gruppi di utenti dall'elenco **AllowedMembers** della categoria come responsabili e membri della chat room per gestire e partecipare alla chat room.

## <a name="tasks-that-you-can-perform"></a>Attività che è possibile eseguire

Nella pagina **Selezionare i membri consentiti** è possibile eseguire le attività seguenti:

- [Configurare le categorie](/previous-versions/office/lync-server-2013/lync-server-2013-configure-categories)

- [Nuove caratteristiche del server chat persistente](/previous-versions/office/lync-server-2013/lync-server-2013-new-persistent-chat-server-features)

Per informazioni dettagliate sulle diverse procedure che è possibile eseguire utilizzando il Pannello di controllo di Skype for Business Server, vedere [Manage Skype for Business Server 2015.](../../manage/manage.md)

## <a name="to-configure-categories-for-chat-rooms"></a>Per configurare le categorie delle chat room

In Appartenenza  , nella sezione Membri consentiti, aggiungere o rimuovere gli utenti e altre entità di Servizi di dominio Active Directory (utenti, gruppi di distribuzione, unità organizzative e così via) che possono essere aggiunti come membri delle chat room appartenenti alla categoria. Le entità consentite da una categoria possono cercare le chat della categoria (a meno che la chat non sia nascosta, caso in cui solo i membri della chat possono cercarla nella directory).


Per informazioni dettagliate sulle funzionalità e sulle funzionalità del server Chat persistente, vedere [Overview of Persistent Chat Server](/previous-versions/office/lync-server-2013/lync-server-2013-overview-of-persistent-chat-server) nella documentazione relativa alla pianificazione. Per informazioni dettagliate sull'utilizzo delle configurazioni del server Chat persistente, vedere [Configuring Persistent Chat Server](/previous-versions/office/lync-server-2013/lync-server-2013-configuring-persistent-chat-server) nella documentazione relativa alla distribuzione e [Managing Lync Server 2013, Persistent Chat Server](/previous-versions/office/lync-server-2013/managing-lync-server-2013-persistent-chat-server) nella documentazione relativa alle operazioni.

## <a name="see-also"></a>Vedere anche

[Informazioni sull'appartenenza di chat persistente](/previous-versions/office/lync-server-2013/understanding-persistent-chat-membership)