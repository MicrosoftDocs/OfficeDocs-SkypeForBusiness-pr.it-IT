---
title: "Lync Server 2013: Configurare i criteri di conferenza per l'accesso esterno"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure conferencing policy for dial-in
ms:assetid: 9bf926d6-0248-4352-98c3-9c5a333debbc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398810(v=OCS.15)
ms:contentKeyID: 48184979
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 74621fee97a1e6721f8772b265761b62b1b9f266
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40984835"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-conferencing-policy-for-dial-in-in-lync-server-2013"></a>Configurare i criteri di conferenza per l'accesso esterno in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2014-03-21_

Criteri di conferenza è un'impostazione dell'account utente che specifica l'esperienza di conferenza per i partecipanti. È possibile creare criteri di conferenza con un ambito del sito o un ambito utente. Le impostazioni dei criteri di conferenza includono molti aspetti della pianificazione e della partecipazione a conferenze. Diverse impostazioni dei criteri di conferenza supportano i servizi di conferenza telefonica con accesso esterno per i partecipanti. Quando si configurano i servizi di conferenza telefonica con accesso esterno, è necessario verificare che questi campi siano impostati in modo appropriato per l'organizzazione e modificarli in base alle esigenze.

Verificare i campi seguenti nei criteri di conferenza:

  - **Consentire ai partecipanti di invitare utenti**   anonimi questa impostazione consente agli organizzatori della riunione di invitare partecipanti anonimi (ovvero non autenticati) alle riunioni. Questa impostazione è facoltativa per i servizi di conferenza telefonica con accesso esterno. Questa impostazione è selezionata per impostazione predefinita nei criteri di conferenza globale predefiniti.

  - **Abilitare i servizi di conferenza telefonica con accesso esterno**   PSTN Questa impostazione consente agli utenti di partecipare alla parte audio di una conferenza effettuando la chiamata dalla rete PSTN. Questa impostazione è necessaria per i servizi di conferenza telefonica con accesso esterno. Questa impostazione è selezionata per impostazione predefinita nei criteri di conferenza globale predefiniti.

  - **Consentire ai partecipanti anonimi di effettuare chiamate in uscita**   questa impostazione consente agli utenti anonimi già iscritti alla riunione di effettuare chiamate in uscita a un numero di telefono per partecipare alla parte audio della conferenza. Questa impostazione è facoltativa per i servizi di conferenza telefonica con accesso esterno. Questa impostazione non è selezionata per impostazione predefinita nei criteri di conferenza globale predefiniti.

  - **Consenti ai partecipanti non abilitati per la chiamata a VoIP aziendale**   questa impostazione consente ai partecipanti e agli organizzatori della riunione che non sono abilitati per VoIP aziendale di effettuare la chiamata a un numero di telefono per partecipare alla parte audio della conferenza. La chiamata esterna è autorizzata in base al criterio vocale assegnato dall'organizzatore. Questa impostazione non è selezionata per impostazione predefinita nei criteri di conferenza globale predefiniti. Il valore predefinito dell'impostazione è disabilitato.
    
    <div>
    

    > [!NOTE]  
    > Per abilitare questa funzionalità, un organizzatore della riunione non abilitato per VoIP aziendale dovrebbe avere un criterio vocale appropriato assegnato per autorizzare qualsiasi chiamata in uscita da una conferenza organizzata dall'utente. Un criterio vocale può essere assegnato a un utente che non è abilitato per VoIP aziendale da Lync Server Management Shell. Se l'utente non ha un criterio vocale assegnato in modo esplicito, il criterio vocale del sito verrà usato per autorizzare la richiesta di chiamata in uscita. Se non è presente alcun criterio vocale del sito, verrà usato il criterio vocale globale.&nbsp;

    
    </div>

La procedura descritta in questa sezione illustra come modificare i criteri di conferenza. Per informazioni dettagliate su come configurare tutte le impostazioni che definiscono l'esperienza dei partecipanti nei criteri di conferenza predefiniti, vedere [creare o modificare una raccolta di impostazioni di configurazione delle riunioni in Lync Server 2013](lync-server-2013-create-or-modify-a-collection-of-meeting-configuration-settings.md). Per informazioni dettagliate su come creare criteri per i servizi di conferenza per un utente o un gruppo di utenti specifico, vedere [creare o modificare criteri per i servizi di conferenza in Lync Server 2013](lync-server-2013-create-or-modify-a-conferencing-policy.md). Per un elenco di tutte le impostazioni dei criteri di conferenza disponibili, vedere informazioni di [riferimento sulle impostazioni per i criteri di conferenza per Lync Server 2013](lync-server-2013-conferencing-policy-settings-reference.md).

<div>

## <a name="to-modify-the-conferencing-policy-for-dial-in"></a>Per modificare i criteri di conferenza per l'accesso esterno

1.  Accedere al computer come membro del gruppo RTCUniversalServerAdmins oppure come membro del ruolo **Cs-ServerAdministrator** o **CsAdministrator** .

2.  Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Sulla barra di spostamento sinistra fare clic su servizi di **conferenza**.

4.  Nella scheda **criteri di conferenza** fare doppio clic su un nome per i criteri di conferenza per aprire la finestra di dialogo **modifica criteri di conferenza** .

5.  Verificare che i campi per i servizi di conferenza telefonica con accesso esterno siano appropriati per l'organizzazione e modificare le impostazioni, se necessario.

6.  Fare clic su **Commit**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

