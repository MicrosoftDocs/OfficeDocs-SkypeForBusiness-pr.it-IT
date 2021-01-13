---
title: Criteri di conferenza creare nuovi o modificarne uno esistente
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
- ms.lync.lscp.ConfMeetingPolicyEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ebd2f120-b57a-4c94-9509-20e098f4b0f4
description: I criteri di conferenza definiscono le caratteristiche e le funzionalità disponibili per gli utenti durante una conferenza (nota anche come riunione).
ms.openlocfilehash: bd4a813bf8b46c9c8dade72318cb003fb97f2a96
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49807456"
---
# <a name="conferencing-policy-create-new-or-edit-existing"></a>Criteri conferenza: crearne di nuovi o modificare quelli esistenti

I criteri di conferenza definiscono le caratteristiche e le funzionalità disponibili per gli utenti durante una conferenza (nota anche come riunione).

## <a name="ui-reference"></a>Riferimenti UI

L'elenco seguente descrive i campi presenti nella pagina.

- **Ambito** Identifica l'ambito dei criteri di conferenza da creare o modificare: globale, sito o utente.

- **Nome** Ogni criterio di conferenza richiede un nome. Ai criteri di conferenza globali e di sito viene assegnato un nome per impostazione predefinita e il nome non può essere modificato. Per i criteri di conferenza utente, usare un nome descrittivo che identifichi l'utente o il gruppo di utenti.

    > [!NOTE]
    > Questo nome non potrà essere modificato dopo aver salvato i criteri di conferenza.

- **Descrizione/Controlli** Questo campo è facoltativo. Usarlo per specificare ulteriori informazioni sui criteri di conferenza.

- **Policy Organizer** Le impostazioni di questa sezione si applicano all'utente che organizza una conferenza. Se un'impostazione è selezionata, l'utente può organizzare una conferenza con la caratteristica specificata. Se un'impostazione non è selezionata, l'utente non può organizzare una conferenza con tale caratteristica. Queste impostazioni non determinano ciò a cui l'utente dispone di accesso come partecipante ad altre conferenze.

    Fare clic sulla freccia rivolta verso l'alto o verso il basso accanto all'etichetta per chiudere o aprire la sezione.

- **Dimensioni massime riunione** numero massimo di utenti consentiti in una conferenza. Per impostazione predefinita, la dimensione massima conferenza è 250.

- **Consenti ai partecipanti di invitare utenti anonimi** Selezionare questa casella di controllo per consentire agli utenti di invitare utenti anonimi alle conferenze. Gli utenti anonimi sono utenti che non dispongono di credenziali nei servizi di dominio Active Directory dell'organizzazione e che, pertanto, non vengono autenticati.

- **Registrazione** Specificare se i partecipanti possono o meno registrare le conferenze. Le opzioni sono **Nessuno** o **Abilita registrazione**.

- **Consenti ai partecipanti anonimi e federati di registrare** Selezionare questa casella di controllo per consentire ai partecipanti esterni e non autenticati di registrare le conferenze.

- **Audio/video** Specificare se i partecipanti possono usare audio e video:

  - **Nessuna** Selezionare questa opzione per impedire l'uso di audio e video.

  - **Abilitare l'audio IP** Selezionare questa opzione per consentire l'uso dell'audio ma non del video.

  - **Abilita audio/video IP** Selezionare questa opzione per consentire l'audio e il video.

- **Abilitare le conferenze telefoniche con accesso esterno PSTN** Se è stato abilitato l'audio in **audio/video**, selezionare questa casella di controllo per consentire agli utenti di effettuare la chiamata a conferenze tramite la rete PSTN (Public Switched Telephone Network).

- **Consenti ai partecipanti anonimi di effettuare chiamate in uscita** Selezionare questa casella di controllo se si consente agli utenti di effettuare la chiamata in conferenze e si desidera consentire agli utenti non autenticati (anonimi) di partecipare a una conferenza utilizzando chiamate in uscita. Con le chiamate in uscita, il server per conferenze chiama l'utente, il quale accede alla conferenza rispondendo al telefono.

- **Consenti ai partecipanti non abilitati per VoIP aziendale di effettuare la chiamata in uscita** Se è stato abilitato l'audio in **audio/video**, selezionare questa casella di controllo per consentire agli utenti che non sono abilitati per VoIP aziendale di partecipare a una conferenza utilizzando il telefono con chiamata in uscita. Con le chiamate in uscita, il server per conferenze chiama l'utente, il quale accede alla conferenza rispondendo al telefono.

- **Consenti più flussi video** Se è stata abilitata la funzionalità video in **audio/video**, selezionare questa casella di controllo per consentire agli utenti di organizzare conferenze con video visualizzazione raccolta. Quando questa casella di controllo è selezionata, questa impostazione consente agli utenti di organizzare conferenze che inviano più flussi video. Quando questa casella di controllo non è selezionata, gli utenti possono organizzare solo conferenze che inviano un singolo flusso video.

    > [!NOTE]
    > Questa opzione determina il tipo di flusso video supportato dalla conferenza, ma non determina il fatto che i partecipanti possano o meno ricevere più flussi video. Questo aspetto è definito dall'opzione **Consenti ai partecipanti di unirsi con più flussi video**.

- **Collaborazione dati** Specificare se la conferenza consente o meno la collaborazione dei dati. Le opzioni sono **Nessuno** o **Abilita collaborazione dati**.

    Le impostazioni seguenti si applicano alla collaborazione dati:

  - **Consenti ai partecipanti anonimi e federati di scaricare contenuto** Se si consente la collaborazione dati, selezionare questa casella di controllo per consentire agli utenti esterni e non autenticati di scaricare contenuti, ad esempio diapositive o stampati, da una conferenza.

  - **Consenti ai partecipanti di trasferire file** Se si consente la collaborazione dati, selezionare questa casella di controllo per consentire i trasferimenti di file a tutti i partecipanti durante una conferenza.

  - **Consenti annotazioni** Se si consente la collaborazione dati, selezionare questa casella di controllo per consentire ai partecipanti di creare annotazioni su schermo sul contenuto condiviso durante la conferenza.

  - **Abilitare le annotazioni di PowerPoint** Se si consentono le annotazioni, selezionare questa casella di controllo per consentire ai partecipanti di creare annotazioni nelle diapositive di PowerPoint condivise durante la conferenza.

  - **Consenti sondaggi** Se si consente la collaborazione dati, selezionare questa casella di controllo per consentire ai partecipanti di svolgere un sondaggio durante una conferenza.

- **Condivisione applicazioni** Specificare se la conferenza consente o meno la condivisione di applicazioni. Le opzioni sono **Disabilita condivisione applicazioni** o **Abilita condivisione applicazioni**.

    Le impostazioni seguenti si applicano alla condivisione di applicazioni:

  - **Consenti ai partecipanti di assumere il controllo** Se si consente la condivisione di applicazioni, selezionare questa casella di controllo per consentire ai partecipanti di assumere il controllo delle applicazioni o dei desktop condivisi durante la conferenza.

  - **Consenti ai partecipanti anonimi e federati di assumere il controllo** Se si consente la condivisione di applicazioni, selezionare questa casella di controllo per consentire ai partecipanti esterni e non autenticati di assumere il controllo delle applicazioni o dei desktop condivisi durante la conferenza.

- **Criterio partecipante** Le impostazioni di questa sezione si applicano agli utenti come partecipanti a una conferenza o a una sessione tra due parti. Poiché le impostazioni seguenti sono relative al singolo utente, un utente di una conferenza o di una sessione tra due parti può disporre di funzionalità diverse rispetto a un altro utente della stessa conferenza o sessione tra due parti.

    Fare clic sulla freccia rivolta verso l'alto o verso il basso accanto all'etichetta per chiudere o aprire la sezione.

- Selezionare **Abilita condivisione applicazioni e desktop** per consentire agli utenti di condividere le applicazioni o il desktop mentre partecipano a una conferenza o a una sessione tra due parti. Selezionare **Disabilita condivisione applicazioni e desktop** per impedire agli utenti di condividere le applicazioni o il desktop mentre partecipano a una conferenza o a una sessione tra due parti.

- **Abilitare il trasferimento di file peer-to-peer** Selezionare questa casella di controllo per consentire i trasferimenti di file da una persona a un'altra, ovvero i trasferimenti di file che non coinvolgono tutti i partecipanti, durante una conferenza o una sessione tra due parti.

- **Abilitare la registrazione peer-to-peer** Selezionare questa casella di controllo per consentire agli utenti di registrare sessioni tra due parti.

- **Consentire ai partecipanti di partecipare a più flussi video** Selezionare questa casella di controllo per consentire ai partecipanti di ricevere video visualizzazione raccolta nelle conferenze che lo consentono. Se questa opzione non è selezionata, i partecipanti possono ricevere solo un singolo flusso video, indipendentemente da ciò che è consentito dalla conferenza.

    > [!NOTE]
    > L'opzione **Consenti più flussi video** determina se una conferenza consente più flussi video.

Per informazioni dettagliate sulle caratteristiche e sulle funzionalità di conferenza, vedere [Overview of Conferencing](https://technet.microsoft.com/library/5bb90e69-3d4f-4d59-a1ee-2550de84439f.aspx) nella documentazione relativa alla pianificazione. Per informazioni dettagliate sull'uso dei criteri di conferenza, vedere [Conferencing Policies](https://technet.microsoft.com/library/8f92eb7c-ee66-4df6-a726-4bff93b122cb.aspx) nella documentazione relativa alle operazioni.


