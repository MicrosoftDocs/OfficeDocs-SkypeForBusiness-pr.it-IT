---
title: Pannello di controllo - Ricerca utente aggiornata
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 5/21/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.UserMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 50feb75f-92a1-4916-b92e-c039e1290c52
description: È possibile utilizzare i risultati di una query di ricerca per configurare gli utenti per Skype for Business Server. È possibile ricercare utenti in base al nome visualizzato, al nome, al cognome, al nome dell'account SAM (Security Accounts Manager), all'indirizzo SIP o all'URI (Uniform Resource Identifier) della linea. È inoltre possibile cercare utenti utilizzando il Pannello di controllo di Lync Server o lo snap-in Utenti e computer di Active Directory.
ms.openlocfilehash: 75e5a3ddf063477351946ad1d5efa1e5877f38d1a6b8d2109fc2b91869bc6cde
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "54320648"
---
# <a name="control-panel---updated-user-search"></a>Pannello di controllo (aggiornato): ricerca utenti

È possibile utilizzare i risultati di una query di ricerca per configurare gli utenti per Skype for Business Server. È possibile ricercare utenti in base al nome visualizzato, al nome, al cognome, al nome dell'account SAM (Security Accounts Manager), all'indirizzo SIP o all'URI (Uniform Resource Identifier) della linea. È inoltre possibile cercare utenti utilizzando il Pannello di controllo di Lync Server o lo snap-in Utenti e computer di Active Directory.

## <a name="tasks-you-can-perform"></a>Attività che è possibile eseguire

Nella pagina Pannello di controllo ricerca utente è possibile **eseguire** le attività seguenti:

- [Cercare utenti di Lync Server 2010](/previous-versions/office/lync-server-2013/lync-server-2013-search-for-lync-server-users)

- [Abilitare o disabilitare gli utenti per Lync Server 2010](/previous-versions/office/lync-server-2013/lync-server-2013-disable-or-re-enable-user-account-for-lync-server)

- [Spostare un utente](move-user.md)

- [Spostare tutti gli utenti](move-all-users.md)

- [Assegnare criteri agli utenti](/previous-versions/office/lync-server-2013/lync-server-2013-assigning-per-user-policies)

- [Abilitare gli utenti VoIP aziendale in Skype for Business Server 2015](../../deploy/deploy-enterprise-voice/enable-users-for-enterprise-voice.md)

- [Configurare la federazione, l'accesso utente remoto e la connettività di messaggistica istantanea pubblica per gli utenti](/previous-versions/office/lync-server-2013/lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user)

- [Configurare telefonia per gli utenti](/previous-versions/office/lync-server-2013/lync-server-2013-configure-telephony-for-a-user)

Per informazioni dettagliate sulle diverse procedure che è possibile eseguire utilizzando il Pannello di controllo di Skype for Business Server, vedere [Manage Skype for Business Server 2015.](../../manage/manage.md)

## <a name="ui-reference"></a>Informazioni sull'interfaccia utente

Nei seguenti elenchi vengono descritti i menu, i comandi, i campi e le proprietà presenti sulla pagina **Ricerca utente**.

### <a name="user-search"></a>Ricerca utente

- **Ricerca** Cercare gli utenti in base alla prima parte del nome visualizzato, del nome, del cognome, del nome dell'account SAM, dell'indirizzo SIP o dell'URI di riga dell'account utente.

- **Ricerca LDAP** Cercare utenti digitando un'espressione LDAP.

- **Casella Cerca utenti** Digitare i dati utente o l'espressione LDAP per cui si desidera eseguire il seach.

- **Trova** Fare clic per visualizzare gli utenti che corrispondono ai valori di ricerca immessi nella **casella Cerca utenti** e.

- **Apri query** Fare clic per aprire una query di ricerca salvata.

- **Salva query** Fare clic per salvare una query di ricerca.

- **+ Aggiungi filtro** Fare clic per aggiungere altri criteri di ricerca.

- **Campi filtro di ricerca** Selezionare il campo in cui si desidera filtrare i risultati della ricerca, selezionare un operatore per la query e quindi digitare la stringa in base alla quale si desidera eseguire la ricerca.

- **Numero massimo di utenti da visualizzare** Digitare il numero di risultati della ricerca che si desidera visualizzare oppure utilizzare le frecce su e giù per specificare il numero.

Aggiungere ulteriore testo descrittivo in base alle necessità.

### <a name="search-results-menus"></a>Menu dei risultati della ricerca

- **Abilitare gli utenti** Fare clic per aprire [la finestra di dialogo Utenti: Nuovo](users-new-lync-server-user.md) utente di Lync Server, in cui è possibile aggiungere un nuovo utente Skype for Business Server.

    Per aggiungere un nuovo contatto, fare clic sulla freccia verso il basso e selezionare **Abilita contatti** per aprire la finestra di dialogo [Users: New Contact Objects](users-new-contact-objects.md).

- **Modifica** Fare **clic su** Modifica e quindi su Mostra dettagli  per visualizzare i dettagli dell'utente selezionato oppure fare clic su Seleziona tutti i risultati della ricerca per selezionare tutti gli utenti visualizzati nella tabella dei risultati. 

- **Azione** Fare **clic su** Azione e quindi selezionare l'azione che si desidera eseguire per gli utenti selezionati nei risultati della ricerca. Sono disponibili le azioni seguenti:

  - **Ri-abilitazione per Lync Server** Abilita l'account utente selezionato dopo che è stato temporaneamente disabilitato.

  - **Disabilitazione temporanea per Lync Server** Disabilita l'account utente in Skype for Business Server finché non viene riattivato, senza rimuovere l'account utente.

  - **Assegnare criteri** Apre la [finestra di dialogo Utenti:](users-assign-policies.md) Assegna criteri, in cui è possibile configurare i criteri assegnati all'utente.

  - **Visualizzare lo stato del PIN** Apre la [finestra di dialogo Utenti: Visualizza stato PIN,](users-view-pin-status.md) che visualizza i dati del PIN per l'utente selezionato.

  - **Imposta PIN** Apre la finestra di dialogo Imposta [PIN,](set-pin.md) in cui è possibile impostare il PIN per l'utente selezionato.

  - **Blocca PIN** Blocca il PIN per l'utente.

  - **Sblocca PIN** Rimuove il blocco sul PIN dell'utente.

  - **Rimuovere da Lync Server** Rimuove l'account utente da Skype for Business Server. L'utente non viene rimosso da Active Directory.

  - **Rimuovere il certificato utente** Rimuove tutti i certificati concessi all'utente.

  - **Spostare gli utenti selezionati nel pool** Apre la [finestra di dialogo](move-user.md) Sposta utente, in cui è possibile selezionare un pool in cui spostare l'utente selezionato.

  - **Spostare tutti gli utenti nel pool** Apre la [finestra di dialogo](move-user.md) Sposta utente, in cui è possibile selezionare un pool in cui spostare tutti gli utenti selezionati.