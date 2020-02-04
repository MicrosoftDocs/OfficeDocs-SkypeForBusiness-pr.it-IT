---
title: 'Lync Server 2013: Rimozione delle autorizzazioni degli utenti autenticati'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Authenticated user permissions are removed
ms:assetid: 5fcd70a5-813a-4076-9bb6-5b0d47505038
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398425(v=OCS.15)
ms:contentKeyID: 48184304
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 63b9761f96156fdc4dea124d4438cdb8685add26
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41722606"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="authenticated-user-permissions-are-removed-in-lync-server-2013"></a>Rimozione delle autorizzazioni degli utenti autenticati in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-02-21_

In un ambiente Active Directory bloccato le voci di controllo di accesso utente autenticate (ACE) vengono rimosse dai contenitori predefiniti di Active Directory, inclusi gli utenti, la configurazione o il sistema e le unità organizzative (OU) in cui l'utente e il computer gli oggetti vengono archiviati. La rimozione degli ACE utente autenticati impedisce l'accesso in lettura alle informazioni di Active Directory. Tuttavia, la rimozione delle voci ACE crea problemi per Lync Server 2013 perché dipende dalle autorizzazioni di lettura per questi contenitori per consentire agli utenti di eseguire la preparazione del dominio.

In questa situazione, l'appartenenza al gruppo Domain Admins, necessaria per eseguire la preparazione del dominio, l'attivazione del server e la creazione di pool, non concede più l'accesso in lettura alle informazioni di Active Directory archiviate nei contenitori predefiniti. È necessario concedere manualmente le autorizzazioni di accesso in lettura per diversi contenitori nel dominio radice della foresta per verificare che la procedura di preparazione della foresta prerequisito sia stata completata.

Per consentire a un utente di eseguire la preparazione del dominio, l'attivazione del server o la creazione di pool in qualsiasi dominio radice non forestale, sono disponibili le opzioni seguenti:

  - Usare un account membro del gruppo amministratori organizzazione per eseguire la preparazione del dominio.

  - Usare un account membro del gruppo Domain Admins e concedere a questo account le autorizzazioni di accesso in lettura per ognuno dei contenitori seguenti nel dominio radice della foresta:
    
      - Dominio
    
      - Configurazione o sistema

Se non si vuole usare un account membro del gruppo amministratori organizzazione per eseguire la preparazione del dominio o altre attività di configurazione, concedere esplicitamente all'account che si vuole usare l'accesso in lettura nei contenitori rilevanti nella radice della foresta.

<div>

## <a name="to-give-users-read-access-permissions-on-containers-in-the-forest-root-domain"></a>Per concedere agli utenti autorizzazioni di accesso in lettura per i contenitori nel dominio radice della foresta

1.  Accedere al computer collegato al dominio radice della foresta con un account membro del gruppo Domain Admins per il dominio radice della foresta.

2.  Eseguire Adsiedit. msc per il dominio radice della foresta.
    
    Se gli ACE utente autenticati sono stati rimossi dal dominio, dalla configurazione o dal contenitore di sistema, è necessario concedere le autorizzazioni di sola lettura al contenitore, come descritto nella procedura seguente.

3.  Fare clic con il pulsante destro del mouse sul contenitore e quindi scegliere **Proprietà**.

4.  Fare clic sulla scheda **sicurezza** .

5.  Fare clic su **Avanzate**.

6.  Nella scheda **autorizzazioni** fare clic su **Aggiungi**.

7.  Digitare il nome dell'utente o del gruppo che riceve le autorizzazioni usando il formato seguente `domain\account name`: e quindi fare clic su **OK**.

8.  Nella scheda **oggetti** , in **si applica a**, fare clic su **solo questo oggetto**.

9.  In **autorizzazioni**selezionare la seguente opzione Consenti ACE facendo clic sul **contenuto** **Consenti** colonna: elenco, **Leggi tutte le proprietà**e **autorizzazioni di lettura**.

10. Fare clic due volte su **OK** .

11. Ripetere questi passaggi per uno dei contenitori pertinenti elencati nel passaggio 2.

</div>

</div>

<span> </span>

</div>

</div>

</div>

