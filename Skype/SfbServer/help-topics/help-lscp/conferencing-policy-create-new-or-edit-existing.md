---
title: Criteri di conferenza creare nuovi o modifica esistenti
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/24/2015
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.ConfMeetingPolicyEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ebd2f120-b57a-4c94-9509-20e098f4b0f4
description: I criteri di conferenza definiscono le caratteristiche e le funzionalità disponibili per gli utenti durante una conferenza, detta anche riunione.
ms.openlocfilehash: 0c3a7a2228afb9ebd401ea99289cb42d6ef7551e
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36190349"
---
# <a name="conferencing-policy-create-new-or-edit-existing"></a>Criteri conferenza: crearne di nuovi o modificare quelli esistenti

I criteri di conferenza definiscono le caratteristiche e le funzionalità disponibili per gli utenti durante una conferenza, detta anche riunione.

## <a name="ui-reference"></a>Riferimenti UI

L'elenco seguente descrive i campi presenti nella pagina.

- **Ambito** Identifica l'ambito dei criteri di conferenza da creare o modificare: globale, sito o utente.

- **Nome** Ogni criterio di conferenza richiede un nome. Ai criteri di conferenza globali e di sito viene assegnato un nome per impostazione predefinita e il nome non può essere modificato. Per i criteri di conferenza utente, usare un nome descrittivo che identifichi l'utente o il gruppo di utenti.

    > [!NOTE]
    > Questo nome non potrà essere modificato dopo aver salvato i criteri di conferenza.

- **Descrizione** Questo campo è facoltativo. Usarlo per specificare ulteriori informazioni sui criteri di conferenza.

- **Criteri organizzazione** Le impostazioni in questa sezione sono valide per l'utente che organizza una conferenza. Se un'impostazione è selezionata, l'utente può organizzare una conferenza con la caratteristica specificata. Se un'impostazione non è selezionata, l'utente non può organizzare una conferenza con tale caratteristica. Queste impostazioni non determinano ciò a cui l'utente può accedere come partecipante in altre conferenze.

    Fare clic sulla freccia rivolta verso l'alto o verso il basso accanto all'etichetta per chiudere o aprire la sezione.

- **Dimensioni massime della riunione** numero massimo di utenti consentiti in una conferenza. Per impostazione predefinita, la dimensione massima della conferenza è 250.

- **Consentire ai partecipanti di invitare utenti anonimi** Selezionare questa casella di controllo per consentire agli utenti di invitare utenti anonimi alle conferenze. Gli utenti anonimi sono utenti che non hanno credenziali nei servizi di dominio Active Directory dell'organizzazione e che, pertanto, non vengono autenticati.

- **Registrazione** Specificare se i partecipanti possono o meno registrare le conferenze. Le opzioni sono **Nessuno** o **Abilita registrazione**.

- **Consentire ai partecipanti federati e anonimi di registrare** Selezionare questa casella di controllo per consentire ai partecipanti esterni e non autenticati di registrare conferenze.

- **Audio/video** Specificare se i partecipanti possono usare l'audio e il video:

  - **Nessuno** Selezionare questa opzione per evitare l'uso di audio e video.

  - **Abilitare l'audio IP** Selezionare questa opzione per consentire l'uso di audio ma non video.

  - **Abilitare l'audio/video IP** Selezionare questa opzione per consentire l'audio e il video.

- **Abilitare i servizi di conferenza telefonica con accesso esterno PSTN** Se è stata abilitata l'audio in **audio/video**, selezionare questa casella di controllo per consentire agli utenti di effettuare chiamate in conferenza tramite la rete PSTN (Public Switched Telephone Network).

- **Consentire ai partecipanti anonimi di effettuare la chiamata in uscita** Selezionare questa casella di controllo se si consente agli utenti di accedere alle conferenze e si vuole consentire agli utenti non autenticati (anonimi) di partecipare a una conferenza tramite chiamata in uscita. Con le chiamate in uscita, il server per conferenze chiama l'utente, il quale accede alla conferenza rispondendo al telefono.

- **Consenti ai partecipanti non abilitati per l'accesso esterno a VoIP aziendale** Se è stata abilitata l'audio in **audio/video**, selezionare questa casella di controllo per consentire agli utenti non abilitati per VoIP aziendale di partecipare a una conferenza tramite chiamata in uscita. Con le chiamate in uscita, il server per conferenze chiama l'utente, il quale accede alla conferenza rispondendo al telefono.

- **Consentire più flussi video** Se è stato abilitato il video in **audio/video**, selezionare questa casella di controllo per consentire agli utenti di organizzare conferenze con il video della visualizzazione raccolta. Quando questa casella di controllo è selezionata, questa impostazione consente agli utenti di organizzare conferenze che inviano più flussi video. Quando questa casella di controllo non è selezionata, gli utenti possono organizzare solo conferenze che inviano un singolo flusso video.

    > [!NOTE]
    > Questa opzione determina il tipo di flusso video supportato dalla conferenza, ma non determina il fatto che i partecipanti possano o meno ricevere più flussi video. Questo aspetto è definito dall'opzione **Consenti ai partecipanti di unirsi con più flussi video**.

- **Collaborazione con i dati** Specificare se la conferenza consente o meno la collaborazione ai dati. Le opzioni sono **Nessuno** o **Abilita collaborazione dati**.

    Le impostazioni seguenti si applicano alla collaborazione dati:

  - **Consentire ai partecipanti federati e anonimi di scaricare contenuto** Se si consente la collaborazione con i dati, selezionare questa casella di controllo per consentire agli utenti esterni e non autenticati di scaricare contenuto, ad esempio diapositive o stampati, da una conferenza.

  - **Consentire ai partecipanti di trasferire file** Se si consente la collaborazione con i dati, selezionare questa casella di controllo per consentire i trasferimenti di file a tutti i partecipanti durante una conferenza.

  - **Abilitare** le annotazioni Se si consente la collaborazione con i dati, selezionare questa casella di controllo per consentire ai partecipanti di effettuare annotazioni su schermo sul contenuto condiviso durante la conferenza.

  - **Abilitare** le annotazioni di PowerPoint Se si consente l'annotazione, selezionare questa casella di controllo per consentire ai partecipanti di creare annotazioni nelle diapositive di PowerPoint condivise durante la conferenza.

  - **Abilitare i sondaggi** Se si consente la collaborazione con i dati, selezionare questa casella di controllo per consentire ai partecipanti di tenere un sondaggio durante una conferenza.

- **Condivisione applicazioni** Specificare se la conferenza consente o meno la condivisione delle applicazioni. Le opzioni sono **Disabilita condivisione applicazioni** o **Abilita condivisione applicazioni**.

    Le impostazioni seguenti si applicano alla condivisione di applicazioni:

  - **Consentire ai partecipanti di assumere il controllo** Se si consente la condivisione di applicazioni, selezionare questa casella di controllo per consentire ai partecipanti di assumere il controllo di applicazioni o desktop condivisi durante la conferenza.

  - **Consentire ai partecipanti federati e anonimi di assumere il controllo** Se si consente la condivisione di applicazioni, selezionare questa casella di controllo per consentire ai partecipanti esterni e non autenticati di assumere il controllo di applicazioni o desktop condivisi durante la conferenza.

- **Criteri** per i partecipanti Le impostazioni in questa sezione si applicano agli utenti come partecipanti a una conferenza o a una sessione di due parti. Poiché le impostazioni seguenti sono relative al singolo utente, un utente di una conferenza o di una sessione tra due parti può disporre di funzionalità diverse rispetto a un altro utente della stessa conferenza o sessione tra due parti.

    Fare clic sulla freccia rivolta verso l'alto o verso il basso accanto all'etichetta per chiudere o aprire la sezione.

- Selezionare **Abilita condivisione applicazioni e desktop** per consentire agli utenti di condividere le applicazioni o il desktop mentre partecipano a una conferenza o a una sessione tra due parti. Selezionare **Disabilita condivisione applicazioni e desktop** per impedire agli utenti di condividere le applicazioni o il desktop mentre partecipano a una conferenza o a una sessione tra due parti.

- **Abilitare il trasferimento di file peer-to-peer** Selezionare questa casella di controllo per consentire i trasferimenti di file da persona a persona, ovvero i trasferimenti di file che non coinvolgono tutti i partecipanti durante una conferenza o una sessione di due parti.

- **Abilitare la registrazione peer-to-peer** Selezionare questa casella di controllo per consentire agli utenti di registrare sessioni in due parti.

- **Consentire ai partecipanti di partecipare con più flussi video** Selezionare questa casella di controllo per consentire ai partecipanti di ricevere il video della visualizzazione raccolta nelle conferenze che lo consentono. Se questa opzione non è selezionata, i partecipanti possono ricevere solo un singolo flusso video, indipendentemente da ciò che è consentito dalla conferenza.

    > [!NOTE]
    > L'opzione **Consenti più flussi video** determina se una conferenza consente più flussi video.

Per informazioni dettagliate sulle caratteristiche e sulle funzionalità di conferenza, vedere [Overview of Conferencing](https://technet.microsoft.com/library/5bb90e69-3d4f-4d59-a1ee-2550de84439f.aspx) nella documentazione relativa alla pianificazione. Per informazioni dettagliate sull'uso dei criteri di conferenza, vedere [Conferencing Policies](https://technet.microsoft.com/library/8f92eb7c-ee66-4df6-a726-4bff93b122cb.aspx) nella documentazione relativa alle operazioni.


