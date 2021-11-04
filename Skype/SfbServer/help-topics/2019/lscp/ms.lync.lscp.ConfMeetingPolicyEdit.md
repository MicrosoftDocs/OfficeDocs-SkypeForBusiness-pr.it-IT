---
title: Criteri conferenza Crea nuovo o Modifica esistente
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.ConfMeetingPolicyEdit
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
ms.localizationpriority: medium
ms.assetid: ebd2f120-b57a-4c94-9509-20e098f4b0f4
ROBOTS: NOINDEX, NOFOLLOW
description: Un criterio di conferenza definisce le funzionalità e le funzionalità che gli utenti hanno a disposizione durante una conferenza (nota anche come riunione).
ms.openlocfilehash: 9d62ac561252c3cda025f040c2de335c49c12bae
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/04/2021
ms.locfileid: "60753015"
---
# <a name="conferencing-policy-create-new-or-edit-existing"></a>Criteri conferenza: crearne di nuovi o modificare quelli esistenti

Un criterio di conferenza definisce le funzionalità e le funzionalità che gli utenti hanno a disposizione durante una conferenza (nota anche come riunione).

## <a name="ui-reference"></a>Riferimenti UI

L'elenco seguente descrive i campi presenti nella pagina.

- **Ambito** Identifica l'ambito del criterio di conferenza che si sta creando o modificando: globale, sito o utente.

- **Nome** Ogni criterio di conferenza richiede un nome. Ai criteri di conferenza globali e di sito viene assegnato un nome per impostazione predefinita e il nome non può essere modificato. Per i criteri di conferenza utente, usare un nome descrittivo che identifichi l'utente o il gruppo di utenti.

    > [!NOTE]
    > Questo nome non potrà essere modificato dopo aver salvato i criteri di conferenza.

- **Descrizione** Questo campo è facoltativo. Usarlo per specificare ulteriori informazioni sui criteri di conferenza.

- **Criterio organizzatore** Le impostazioni di questa sezione si applicano all'utente che organizza una conferenza. Se un'impostazione è selezionata, l'utente può organizzare una conferenza con la caratteristica specificata. Se un'impostazione non è selezionata, l'utente non può organizzare una conferenza con tale caratteristica. Queste impostazioni non determinano ciò a cui l'utente dispone di accesso come partecipante ad altre conferenze.

    Fare clic sulla freccia rivolta verso l'alto o verso il basso accanto all'etichetta per chiudere o aprire la sezione.

- **Dimensioni massime riunione** il numero massimo di utenti consentiti in una conferenza. Per impostazione predefinita, la dimensione massima della conferenza è 250.

- **Consentire ai partecipanti di invitare utenti anonimi** Selezionare questa casella di controllo per consentire agli utenti di invitare utenti anonimi alle conferenze. Gli utenti anonimi sono utenti che non dispongono di credenziali in Servizi di dominio Active Directory dell'organizzazione e che pertanto non sono autenticati.

- **Registrazione** Specificare se i partecipanti possono registrare le conferenze. Le opzioni sono **Nessuno** o **Abilita registrazione**.

- **Consentire ai partecipanti federati e anonimi di registrare** Selezionare questa casella di controllo per consentire ai partecipanti esterni e non autenticati di registrare le conferenze.

- **Audio/video** Specificare se i partecipanti possono utilizzare audio e video:

  - **Nessuno** Selezionare questa opzione per impedire l'uso di audio e video.

  - **Abilitare l'audio IP** Selezionare questa opzione per consentire l'uso di audio ma non video.

  - **Abilita audio/video IP** Selezionare questa opzione per consentire sia l'audio che il video.

- **Abilitare le conferenze telefoniche con accesso esterno PSTN** Se l'audio è stato abilitato in **Audio/video,** selezionare questa casella di controllo per consentire agli utenti di accedere alle conferenze utilizzando la rete PSTN (Public Switched Telephone Network).

- **Consentire ai partecipanti anonimi di effettuare chiamate in uscita** Selezionare questa casella di controllo se si consente agli utenti di accedere alle conferenze e si desidera consentire agli utenti non autenticati (anonimi) di partecipare a una conferenza tramite chiamate in uscita. Con le chiamate in uscita, il server per conferenze chiama l'utente, il quale accede alla conferenza rispondendo al telefono.

- **Consenti ai partecipanti non abilitati VoIP aziendale chiamate in uscita** Se è stato abilitato l'audio in **Audio/video,** selezionare questa casella di controllo per consentire agli utenti non abilitati per VoIP aziendale di partecipare a una conferenza tramite chiamate in uscita. Con le chiamate in uscita, il server per conferenze chiama l'utente, il quale accede alla conferenza rispondendo al telefono.

- **Consentire più flussi video** Se è stato abilitato il video in **Audio/video,** selezionare questa casella di controllo per consentire agli utenti di organizzare conferenze con video visualizzazione Raccolta. Quando questa casella di controllo è selezionata, questa impostazione consente agli utenti di organizzare conferenze che inviano più flussi video. Quando questa casella di controllo non è selezionata, gli utenti possono organizzare solo conferenze che inviano un singolo flusso video.

    > [!NOTE]
    > Questa opzione determina il tipo di flusso video supportato dalla conferenza, ma non determina il fatto che i partecipanti possano o meno ricevere più flussi video. Questo aspetto è definito dall'opzione **Consenti ai partecipanti di unirsi con più flussi video**.

- **Collaborazione dati** Specificare se la conferenza consente o meno la collaborazione dati. Le opzioni sono **Nessuno** o **Abilita collaborazione dati**.

    Le impostazioni seguenti si applicano alla collaborazione dati:

  - **Consentire ai partecipanti federati e anonimi di scaricare contenuto** Se si consente la collaborazione dati, selezionare questa casella di controllo per consentire agli utenti esterni e non autenticati di scaricare contenuto, ad esempio diapositive o stampati, da una conferenza.

  - **Consenti ai partecipanti di trasferire file** Se si consente la collaborazione dati, selezionare questa casella di controllo per consentire il trasferimento di file a tutti i partecipanti durante una conferenza.

  - **Abilitare le annotazioni** Se si consente la collaborazione dati, selezionare questa casella di controllo per consentire ai partecipanti di creare annotazioni su schermo sul contenuto condiviso durante la conferenza.

  - **Abilitare PowerPoint annotazioni** Se si consente l'annotazione, selezionare questa casella di controllo per consentire ai partecipanti di creare annotazioni nelle diapositive PowerPoint condivise durante la conferenza.

  - **Abilitare i polling** Se si consente la collaborazione dati, selezionare questa casella di controllo per consentire ai partecipanti di tenere un sondaggio durante una conferenza.

- **Condivisione applicazioni** Specificare se la conferenza consente o meno la condivisione delle applicazioni. Le opzioni sono **Disabilita condivisione applicazioni** o **Abilita condivisione applicazioni**.

    Le impostazioni seguenti si applicano alla condivisione di applicazioni:

  - **Consentire ai partecipanti di assumere il controllo** Se si consente la condivisione delle applicazioni, selezionare questa casella di controllo per consentire ai partecipanti di assumere il controllo delle applicazioni o dei desktop condivisi durante la conferenza.

  - **Consentire ai partecipanti federati e anonimi di assumere il controllo** Se si consente la condivisione di applicazioni, selezionare questa casella di controllo per consentire ai partecipanti esterni e non autenticati di assumere il controllo delle applicazioni o dei desktop condivisi durante la conferenza.

- **Criteri partecipante** Le impostazioni di questa sezione si applicano agli utenti come partecipanti a una conferenza o a una sessione tra due parti. Poiché le impostazioni seguenti sono relative al singolo utente, un utente di una conferenza o di una sessione tra due parti può disporre di funzionalità diverse rispetto a un altro utente della stessa conferenza o sessione tra due parti.

    Fare clic sulla freccia rivolta verso l'alto o verso il basso accanto all'etichetta per chiudere o aprire la sezione.

- Selezionare **Abilita condivisione applicazioni e desktop** per consentire agli utenti di condividere le applicazioni o il desktop mentre partecipano a una conferenza o a una sessione tra due parti. Selezionare **Disabilita condivisione applicazioni e desktop** per impedire agli utenti di condividere le applicazioni o il desktop mentre partecipano a una conferenza o a una sessione tra due parti.

- Abilitare il trasferimento di **file peer-to-peer** Selezionare questa casella di controllo per consentire trasferimenti di file da persona a persona, ovvero trasferimenti di file che non coinvolgono tutti i partecipanti, durante una conferenza o una sessione tra due parti.

- **Abilitare la registrazione peer-to-peer** Selezionare questa casella di controllo per consentire agli utenti di registrare sessioni tra due parti.

- **Consentire ai partecipanti di partecipare a più flussi video** Selezionare questa casella di controllo per consentire ai partecipanti di ricevere video della visualizzazione Raccolta nelle conferenze che lo consentono. Se questa opzione non è selezionata, i partecipanti possono ricevere solo un singolo flusso video, indipendentemente da ciò che è consentito dalla conferenza.

    > [!NOTE]
    > L'opzione **Consenti più flussi video** determina se una conferenza consente più flussi video.

Per informazioni dettagliate sulle caratteristiche e sulle funzionalità di conferenza, vedere [Overview of Conferencing](/previous-versions/office/lync-server-2013/lync-server-2013-overview-of-conferencing) nella documentazione relativa alla pianificazione. Per informazioni dettagliate sull'uso dei criteri di conferenza, vedere [Conferencing Policies](/previous-versions/office/lync-server-2013/lync-server-2013-conferencing-policies) nella documentazione relativa alle operazioni.