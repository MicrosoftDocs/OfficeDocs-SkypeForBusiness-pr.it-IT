---
title: Pagina principale del componente aggiuntivo Chat persistente
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.PersistentChatAddinMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0c0ecf64-258d-4b43-8fac-fa5ffa4e7646
description: È possibile usare la sezione componente aggiuntivo della pagina della chat persistente per associare gli URL alle chat room permanenti. Questi URL verranno visualizzati nel riquadro di estendibilità delle conversazioni della chat room del client. Perché gli utenti possano visualizzare questo aggiornamento nel proprio client, l'amministratore deve aggiungere componenti aggiuntivi all'elenco dei componenti aggiuntivi registrati, mentre i responsabili/creatori della chat room devono associare chat a uno dei componenti aggiuntivi registrati.
ms.openlocfilehash: 60cf60c6f6691725161182c5cc4e5c2fd38a0576
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41822579"
---
# <a name="persistent-chat-add-in-main-page"></a>Pagina principale del componente aggiuntivo Chat persistente

È possibile usare la sezione **componente aggiuntivo** della pagina della **chat persistente** per associare gli URL alle chat room permanenti. Questi URL verranno visualizzati nel riquadro di estendibilità delle conversazioni della chat room del client. Perché gli utenti possano visualizzare questo aggiornamento nel proprio client, l'amministratore deve aggiungere componenti aggiuntivi all'elenco dei componenti aggiuntivi registrati, mentre i responsabili/creatori della chat room devono associare chat a uno dei componenti aggiuntivi registrati.

I componenti aggiuntivi sono usati per ampliare l'esperienza all'interno della chat. Un componente aggiuntivo tipico può includere un URL che punta a un'applicazione Silverlight che intercetta quando un ticker del titolo viene inserito in una chat room e Mostra la cronologia del titolo nel riquadro estensibilità. Altri esempi sono l'incorporamento di un URL di OneNote 2013 nella chat room come componente aggiuntivo per includere contenuto condiviso, ad esempio "In primo piano" o "Argomento del giorno".

Per creare componenti aggiuntivi per le chat room permanenti, vedere [configurare i componenti aggiuntivi per le chat room permanenti in Skype for Business Server 2015](../../manage/persistent-chat/configure-add-ins.md). Se si è un amministratore della chat persistente, è possibile creare componenti aggiuntivi usando il pannello di controllo o i cmdlet di Windows PowerShell.

## <a name="tasks-you-can-perform"></a>Attività che è possibile eseguire

Nella pagina **Componente aggiuntivo** è possibile eseguire le attività seguenti:

- [Configurare i componenti aggiuntivi per le chat room di Chat persistente](../../manage/persistent-chat/configure-add-ins.md)

## <a name="to-configure-add-ins-for-chat-rooms"></a>Per configurare componenti aggiuntivi per le chat room

Gli elenchi seguenti descrivono i menu, i comandi, i campi e le proprietà della pagina.

1. Da un account utente assegnato al ruolo CsPersistentChatAdministrator o CsAdministrator, accedere a un qualsiasi computer nella distribuzione interna.

2. Nel menu **Start** selezionare il pannello di controllo di Skype for Business Server o aprire una finestra del browser e quindi immettere l'URL dell'amministratore. Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il Pannello di controllo, vedere [Open Lync Server Administrative Tools](https://technet.microsoft.com/library/8c58de94-9e0a-4368-9e14-9afcaa1142d0.aspx).

3. Sulla barra di spostamento sinistra fare clic su **Chat persistente** e quindi su **Componente aggiuntivo**.

    Per più distribuzioni di pool di server di chat persistenti, selezionare il pool appropriato nell'elenco a discesa.

4. Nella pagina **Componente aggiuntivo** fare clic su **Nuovo**.

5. In **Seleziona un servizio**selezionare il servizio corrispondente al pool del server di chat persistente in cui è necessario creare il componente aggiuntivo. I componenti aggiuntivi non possono essere spostati da un pool a un altro o condivisi da pool diversi.

6. In **Nuovo componente aggiuntivo** eseguire le operazioni seguenti:

   - In **Nome** specificare un nome per il nuovo componente aggiuntivo.

   - In **URL** specificare l'URL da associare al componente aggiuntivo. Gli URL devono limitarsi ai protocolli http e https.

7. Fare clic su **Commit**.

## <a name="see-also"></a>Vedere anche

Per informazioni dettagliate sulle funzionalità e le funzionalità del server di chat persistente, vedere [pianificare il server di chat persistente in Skype for Business server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md), [distribuire il server di chat persistente in Skype for Business Server 2015](../../deploy/deploy-persistent-chat-server/deploy-persistent-chat-server.md)e [gestire il server di chat persistente in Skype for Business Server 2015](../../manage/persistent-chat/persistent-chat.md).


