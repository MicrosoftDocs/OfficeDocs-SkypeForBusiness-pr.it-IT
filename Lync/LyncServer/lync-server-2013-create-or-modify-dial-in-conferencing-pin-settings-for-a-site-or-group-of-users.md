---
title: 'Lync Server 2013: Creare o modificare le impostazioni del PIN di conferenza telefonica con accesso esterno per un sito o un gruppo di utenti'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create or modify dial-in conferencing PIN settings for a site or group of users
ms:assetid: c29bab5c-2b93-48e0-ae0b-29564daaff9a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412959(v=OCS.15)
ms:contentKeyID: 48185326
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2af1dc8e3f9bde06e799c758b711f94b7c0e6411
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40984188"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-dial-in-conferencing-pin-settings-in-lync-server-2013-for-a-site-or-group-of-users"></a>Creare o modificare le impostazioni del PIN di conferenza telefonica con accesso esterno in Lync Server 2013 per un sito o un gruppo di utenti

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-10-18_

Seguire questa procedura per creare o modificare un criterio PIN (Personal Identification Number) dei servizi di conferenza telefonica con accesso esterno a livello di utente o a livello di sito. Per informazioni dettagliate su come modificare il criterio PIN globale, vedere [modificare le impostazioni predefinite dei pin per i servizi di conferenza telefonica con accesso esterno in Lync Server 2013](lync-server-2013-modify-the-default-dial-in-conferencing-pin-settings.md).

<div>

## <a name="to-create-a-user-or-site-pin-policy"></a>Per creare un criterio PIN per un utente o un sito

1.  Da un account utente che è un membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) o assegnato al ruolo CsServerAdministrator o CsAdministrator, accedere a qualsiasi computer presente nella rete in cui è stato distribuito Lync Server 2013.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Sulla barra di spostamento sinistra fare clic su servizi di **conferenza**e quindi su **criteri PIN**.

4.  Nella pagina **criteri PIN** fare clic su **nuovo**e quindi eseguire una delle operazioni seguenti:
    
      - Per creare un criterio a livello di utente, fare clic su **criteri utente**. In **nome**digitare un nome che descriva il criterio in **nuovo criterio PIN**.
    
      - Per creare un criterio a livello di sito, fare clic su **criteri sito**. Nel campo **Seleziona ricerca sito** digitare tutto o parte del nome del sito per cui si vuole creare un criterio. Nell'elenco dei siti fare clic sul sito desiderato e quindi fare clic su **OK**.

5.  Nel campo **Descrizione** Digitare una descrizione del criterio PIN.

6.  Nel campo **lunghezza minima PIN** Digitare o selezionare la lunghezza minima del PIN che si vuole consentire. La lunghezza minima predefinita è di cinque cifre.

7.  Per poter specificare il numero massimo di tentativi di accesso prima che un utente venga bloccato, selezionare la casella di controllo **specifica tentativi di accesso massimo** . Se non si seleziona questa opzione, il numero massimo di tentativi consentiti viene determinato automaticamente in base alla lunghezza del PIN. Per impostazione predefinita, il numero massimo di tentativi viene determinato automaticamente.

8.  Se è stata selezionata la casella di controllo **specifica tentativi di accesso massimo** , in **tentativi di accesso massimo**digitare o selezionare il numero massimo di tentativi di accesso che si desidera consentire.

9.  Per impostare i pin in scadenza, selezionare la casella di controllo **Abilita scadenza PIN** . Se non si seleziona questa opzione, i pin non scadono mai. Per impostazione predefinita, i pin non scadono mai.

10. Se è stata selezionata la casella di controllo **Abilita scadenza PIN** , in **PIN scade dopo (giorni)** digitare o selezionare il numero di giorni dopo il quale i pin scadono.

11. In **conteggio cronologia PIN**Digitare il numero di pin che un utente deve creare prima che l'utente possa riutilizzare un PIN. Per impostazione predefinita, gli utenti possono riutilizzare i loro PIN.

12. Per consentire modelli comuni di cifre nei pin, ad esempio numeri sequenziali e set ripetitivi di numeri, selezionare la casella di controllo **Consenti schemi comuni** . Se non si seleziona questa opzione, sono consentiti solo modelli complessi di cifre. Per impostazione predefinita, sono consentiti solo modelli complessi di cifre.
    
    <div>
    

    > [!IMPORTANT]
    > È consigliabile non consentire modelli comuni.

    
    </div>

13. Fare clic su **Commit**.

</div>

<div>

## <a name="to-change-a-user-or-site-pin-policy"></a>Per modificare un criterio PIN per un utente o un sito

1.  Da un account utente che è un membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) o assegnato al ruolo CsServerAdministrator o CsAdministrator, accedere a qualsiasi computer presente nella rete in cui è stato distribuito Lync Server 2013.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Sulla barra di spostamento sinistra fare clic su servizi di **conferenza**e quindi su **criteri PIN**.

4.  Nella pagina **criteri PIN** fare clic sul criterio PIN che si vuole modificare, fare clic su **modifica**e quindi su **Mostra dettagli**.

5.  In **modifica criterio PIN**modificare le impostazioni dei criteri (ad eccezione del nome del criterio, che non può essere modificato).

6.  Fare clic su **Commit**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

