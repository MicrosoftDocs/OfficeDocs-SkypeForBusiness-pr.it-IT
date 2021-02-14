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
description: La creazione e la gestione delle chat room di Persistent Chat sono molto più semplici con l'uso corretto delle categorie. Un amministratore di Persistent Chat può definire AllowedMembers e Creators per ogni categoria e può anche definire le impostazioni e i comportamenti predefiniti delle chat room che verranno applicati a tutte le chat room create nella categoria. Gli amministratori di Persistent Chat creano e gestiscono categorie utilizzando il Pannello di controllo o Windows PowerShell cmdlet.
ms.openlocfilehash: 8c45a16f88bf20ab973927e17807b3241f20e942
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49829136"
---
# <a name="select-allowed-members"></a>Selezionare membri consentiti

La creazione e la gestione delle chat room di Persistent Chat sono molto più semplici con l'uso corretto delle categorie. Un amministratore di Persistent Chat può definire **AllowedMembers** e **Creators** per ogni categoria e può anche definire le impostazioni e i comportamenti predefiniti delle chat room che verranno applicati a tutte le chat room create nella categoria. Gli amministratori di Persistent Chat creano e gestiscono categorie utilizzando il Pannello di controllo o Windows PowerShell cmdlet.

Utenti, unità organizzative e gruppi di utenti identificati come creatori della categoria sono gli unici individui e gruppi a cui è consentito creare chat nella categoria. Dopo aver creato la categoria, possono scegliere utenti, unità organizzative e gruppi di utenti nell'elenco **AllowedMembers** della categoria come responsabili e membri della chat room per gestire e partecipare alla chat room.

## <a name="tasks-that-you-can-perform"></a>Attività che è possibile eseguire

Nella pagina **Selezionare i membri consentiti** è possibile eseguire le attività seguenti:

- [Configurare le categorie](https://technet.microsoft.com/library/4547f514-f0c0-404d-890f-092ddeeac852.aspx)

- [Nuove caratteristiche del server chat persistente](https://technet.microsoft.com/library/c3ec6f33-6261-4bf5-aa31-baa8ab2a87d8.aspx)

Per informazioni dettagliate sulle diverse procedure che è possibile eseguire utilizzando il Pannello di controllo di Skype for Business Server, vedere [Gestire Skype for Business Server 2015.](../../manage/manage.md)

## <a name="to-configure-categories-for-chat-rooms"></a>Per configurare le categorie delle chat room

In Appartenenza,  nella sezione Membri consentiti aggiungere o rimuovere utenti e altre entità di Servizi di dominio Active Directory (utenti, gruppi di distribuzione, unità organizzative e così via) che possono essere aggiunti come membri delle chat room appartenenti alla categoria. Le entità consentite da una categoria possono cercare le chat della categoria (a meno che la chat non sia nascosta, caso in cui solo i membri della chat possono cercarla nella directory).


Per informazioni dettagliate sulle caratteristiche e sulle funzionalità del server Chat persistente, vedere [Overview of Persistent Chat Server](https://technet.microsoft.com/library/23f7c886-304d-495a-ae70-3cbb44241acd.aspx) nella documentazione relativa alla pianificazione. Per informazioni dettagliate sull'utilizzo delle configurazioni del server Chat persistente, vedere [Configuring Persistent Chat Server](https://technet.microsoft.com/library/d90a4049-b268-4e8e-9f24-0cef08c8d9ed.aspx) nella documentazione relativa alla distribuzione e [Managing Lync Server 2013, Persistent Chat Server](https://technet.microsoft.com/library/82befdc6-5d32-45f1-bfd7-aaedffed1ab8.aspx) nella documentazione relativa alle operazioni.

## <a name="see-also"></a>Vedere anche

[Informazioni sull'appartenenza di chat persistente](https://technet.microsoft.com/library/900392d6-6e9f-4dae-93d6-39d7474409ef.aspx)
