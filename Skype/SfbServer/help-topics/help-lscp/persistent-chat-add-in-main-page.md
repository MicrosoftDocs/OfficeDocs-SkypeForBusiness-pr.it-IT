---
title: Pagina principale del componente aggiuntivo Persistent Chat
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.PersistentChatAddinMain
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 0c0ecf64-258d-4b43-8fac-fa5ffa4e7646
description: È possibile utilizzare la sezione Componente aggiuntivo della pagina Persistent Chat per associare GLI URL alle chat room di Persistent Chat. Questi URL vengono visualizzati nel client nella chat room nel riquadro di estendibilità della conversazione. Un amministratore deve aggiungere componenti aggiuntivi all'elenco dei componenti aggiuntivi registrati e i responsabili/creatori di chat devono associare le chat room a uno dei componenti aggiuntivi registrati prima che gli utenti possano visualizzare questo aggiornamento nel client.
ms.openlocfilehash: 0d3f09ee5f2ab130a54d60424ee2966d36e54142
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/26/2021
ms.locfileid: "58614346"
---
# <a name="persistent-chat-add-in-main-page"></a>Pagina principale del componente aggiuntivo di Chat persistente

È possibile utilizzare la **sezione Componente aggiuntivo** della pagina Persistent **Chat** per associare GLI URL alle chat room di Persistent Chat. Questi URL vengono visualizzati nel client nella chat room nel riquadro di estendibilità della conversazione. Un amministratore deve aggiungere componenti aggiuntivi all'elenco dei componenti aggiuntivi registrati e i responsabili/creatori di chat devono associare le chat room a uno dei componenti aggiuntivi registrati prima che gli utenti possano visualizzare questo aggiornamento nel client.

I componenti aggiuntivi vengono utilizzati per estendere l'esperienza in chat. Un componente aggiuntivo tipico può includere un URL che punta a un'applicazione Silverlight che intercetta quando un ticker di azioni viene pubblicato in una chat room e mostra la cronologia delle azioni nel riquadro di estendibilità. Tra gli altri esempi c'è l'integrazione di un URL OneNote 2013 nella chat room in forma di componente aggiuntivo, per includere un contesto condiviso, ad esempio "Di facile riconoscibilità" o "Argomento del giorno".

Per creare componenti aggiuntivi per chat room persistenti, vedere [Configure add-ins for Persistent Chat rooms in Skype for Business Server 2015.](../../manage/persistent-chat/configure-add-ins.md) Gli amministratori di Persistent Chat possono creare componenti aggiuntivi utilizzando il Pannello di controllo o Windows PowerShell cmdlet.

## <a name="tasks-you-can-perform"></a>Attività eseguibili

Nella pagina **Componente aggiuntivo** è possibile eseguire le attività seguenti:

- [Configurare i componenti aggiuntivi per le chat room di Persistent Chat in Skype for Business Server 2015](../../manage/persistent-chat/configure-add-ins.md)

## <a name="to-configure-add-ins-for-chat-rooms"></a>Per configurare componenti aggiuntivi per chat room

Nei seguenti elenchi vengono descritti i menu, i comandi, i campi e le proprietà presenti sulla pagina.

1. Da un account utente assegnato al ruolo CsPersistentChatAdministrator o CsAdministrator accedere a uno qualsiasi dei computer della distribuzione interna.

2. Dal menu **Start** seleziona il pannello di Skype for Business Server o apri una finestra del browser e quindi immetti l'URL di amministratore. Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il Pannello di controllo, vedere [Open Lync Server Administrative Tools](/previous-versions/office/lync-server-2013/lync-server-2013-open-lync-server-administrative-tools).

3. Sulla barra di spostamento sinistra fare clic su **Persistent Chat** e quindi su **Componente aggiuntivo**.

    Per più distribuzioni di pool di server Chat persistente, selezionare il pool appropriato nell'elenco a discesa.

4. Nella pagina **Componente aggiuntivo** fare clic su **Nuovo**.

5. In **Selezionare un servizio** selezionare il servizio corrispondente al pool di server Chat persistente in cui è necessario creare il componente aggiuntivo. I componenti aggiuntivi non possono essere spostati da un pool all'altro o condivisi tra diversi pool.

6. In **Nuovo componente aggiuntivo** eseguire le operazioni seguenti:

   - In **Nome** specificare un nome per il nuovo componente aggiuntivo.

   - In **URL** specificare l'URL da associare al componente aggiuntivo. Gli URL sono limitati ai protocolli http e https.

7. Fare clic su **Commit**.

## <a name="see-also"></a>Vedere anche

Per informazioni dettagliate sulle funzionalità e sulle funzionalità del server Chat persistente, vedere [Plan for Persistent Chat Server in Skype for Business Server 2015,](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)Deploy Persistent Chat Server in Skype for Business Server [2015](../../deploy/deploy-persistent-chat-server/deploy-persistent-chat-server.md)e [Manage Persistent Chat Server in Skype for Business Server 2015.](../../manage/persistent-chat/persistent-chat.md)