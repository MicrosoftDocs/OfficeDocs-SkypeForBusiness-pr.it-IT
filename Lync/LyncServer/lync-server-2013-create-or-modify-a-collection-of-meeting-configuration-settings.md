---
title: Creare o modificare una raccolta di impostazioni di configurazione delle riunioni
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create or modify a collection of meeting configuration settings
ms:assetid: ce6773c1-a0d5-4405-8e32-33a6f3a46a1a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721889(v=OCS.15)
ms:contentKeyID: 49733822
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2b948d5aded2447e5319378a613fdf474c3e5450
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40978017"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-collection-of-meeting-configuration-settings-in-lync-server-2013"></a>Creare o modificare una raccolta di impostazioni di configurazione delle riunioni in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-02-23_

È possibile usare le impostazioni nella pagina Configurazione riunione per definire le varie caratteristiche dell'esperienza di partecipazione alla riunione. Per impostazione predefinita, le impostazioni globali definiscono l'esperienza di partecipazione. È anche possibile creare impostazioni di riunione a livello di sito e a livello di pool. Se crei impostazioni a livello di pool, queste impostazioni si applicano a tutte le riunioni ospitate da tale pool. Se non si creano impostazioni a livello di pool, le impostazioni a livello di sito si applicano, se esistenti. Se non si definiscono le impostazioni a livello di sito, le impostazioni globali si applicano a tutte le riunioni.

<div>

## <a name="to-create-new-meeting-join-settings"></a>Per creare nuove impostazioni di partecipazione alle riunioni

1.  Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer della distribuzione interna.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Sulla barra di spostamento sinistra fare clic su **conferenza** e quindi su **Configurazione riunione**.

4.  Nella pagina **Configurazione riunione** fare clic su **nuovo**e quindi eseguire una delle operazioni seguenti:
    
      - Per creare un criterio a livello di sito, fare clic su **configurazione sito**. Nel campo **Seleziona ricerca sito** digitare tutto o parte del nome del sito per il quale si desidera definire le impostazioni di partecipazione alle riunioni. Nell'elenco dei siti risultante fare clic sul sito desiderato e quindi fare clic su **OK**.
    
      - Per creare criteri a livello di pool, fare clic su **Configurazione pool**. Nel campo **selezionare un servizio** di ricerca digitare tutto o parte del nome del servizio pool per cui si desidera definire le impostazioni di partecipazione alle riunioni. Nell'elenco dei servizi risultante fare clic sul pool desiderato e quindi fare clic su **OK**.

5.  Per instradare i partecipanti che effettuano la chiamata tramite la rete PSTN (Public Switched Telephone Network) nella sala di attesa, deselezionare la casella di controllo **Ignora chiamate PSTN** . Per impostazione predefinita, i partecipanti che effettuano la chiamata dalla rete PSTN accedono direttamente alla riunione.

6.  Per configurare chi può essere un relatore nella riunione, in **designa come relatore**eseguire una delle operazioni seguenti:
    
      - Per non consentire a utenti diversi dall'organizzatore di essere relatori, fare clic su **nessuno**.
    
      - Per consentire solo ai partecipanti membri dell'organizzazione di essere relatori, fare clic su **società**. Questa è l'impostazione predefinita.
    
      - Per consentire a tutti i partecipanti di essere un relatore, fare clic su **tutti**.

7.  Per fare in modo che l'organizzatore selezioni un tipo di conferenza durante la programmazione di una riunione, deselezionare la casella **di controllo tipo di conferenza assegnata per impostazione predefinita** . Per impostazione predefinita, il tipo di conferenza viene assegnato automaticamente.

8.  Per impedire l'ammissione automatica degli utenti anonimi (non autenticati), deselezionare la casella **di controllo Ammetti gli utenti anonimi per impostazione predefinita** . Per impostazione predefinita, gli utenti anonimi vengono ammessi automaticamente alle riunioni.

9.  Per personalizzare l'invito alla riunione inviato ai partecipanti, eseguire le operazioni seguenti. Tieni presente che la lunghezza massima per gli URL e il testo del piè di pagina personalizzato è 1KB. Ad eccezione dell' **URL della Guida**, se non si specifica un valore per le personalizzazioni, questi non verranno inclusi nella riunione. Se non si include un URL della Guida personalizzato, l'URL della Guida predefinito per Lync verrà visualizzato nell'invito.
    
      - Per personalizzare il logo visualizzato nell'invito alla riunione, in **URL logo**immettere la posizione del logo.
        
        <div>
        

        > [!NOTE]
        > Il logo deve essere un'immagine GIF o JPG con una dimensione di 188 di 30 pixel.

        
        </div>
    
      - Per personalizzare il testo della Guida visualizzato nell'invito alla riunione, in **URL della Guida**immettere la posizione del testo della guida.
    
      - Per personalizzare il testo legale visualizzato nell'invito alla riunione, in **URL di testo legale**immettere la posizione del testo legale.
    
      - Per personalizzare il testo del piè di pagina visualizzato nell'invito alla riunione, nel **testo del piè**di pagina personalizzato immettere il testo.

10. Fare clic su **Commit**.

</div>

<div>

## <a name="to-modify-an-existing-collection-of-meeting-configurations"></a>Per modificare una raccolta esistente di configurazioni di riunione

1.  Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer della distribuzione interna.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Sulla barra di spostamento sinistra fare clic su **conferenza** e quindi su **Configurazione riunione**.

4.  Nell'elenco delle configurazioni delle riunioni fare clic sulla configurazione che si vuole modificare, fare clic su **modifica**e quindi su **Mostra dettagli**.

5.  In **modifica configurazione riunione**modificare le impostazioni di configurazione, ad eccezione del nome della configurazione, che non può essere modificato.

6.  Fare clic su **Commit**.

</div>

<div>

## <a name="creating-new-meeting-configuration-settings-by-using-windows-powershell-cmdlets"></a>Creazione di nuove impostazioni di configurazione delle riunioni con i cmdlet di Windows PowerShell

Le impostazioni di configurazione della riunione possono essere create (solo nell'ambito del sito) tramite Windows PowerShell e il cmdlet New-CsMeetingConfiguration. Questo cmdlet può essere eseguito da Lync Server 2013 Management Shell o da una sessione remota di Windows PowerShell. Per informazioni dettagliate sull'uso di Windows PowerShell remoto per la connessione a Lync Server, vedere l'articolo sul Blog di Lync Server di Windows PowerShell "Guida introduttiva: gestione di Microsoft [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Lync Server 2010 con Remote PowerShell" at.

<div>

## <a name="to-create-meeting-configuration-settings-that-use-the-default-values"></a>Per creare impostazioni di configurazione delle riunioni che usano i valori predefiniti

  - Questo comando crea un nuovo set di impostazioni di configurazione delle riunioni per il sito Redmond:
    
        New-CsMeetingConfiguration -Identity "site:Redmond"
    
    Poiché non sono stati specificati parametri (ad eccezione del parametro di identità obbligatorio) nel comando precedente, le nuove impostazioni di configurazione della riunione utilizzeranno i valori predefiniti per tutte le relative proprietà.

</div>

<div>

## <a name="to-change-a-property-value-when-creating-meeting-configuration-settings"></a>Per modificare un valore di proprietà durante la creazione delle impostazioni di configurazione delle riunioni

  - Per creare impostazioni che usano valori di proprietà diversi, includere semplicemente il parametro e il valore del parametro appropriati. Ad esempio, per creare una raccolta di impostazioni di configurazione della riunione che, per impostazione predefinita, ammettono tutti a una riunione come relatore usare un comando come questo:
    
        New-CsMeetingConfiguration -Identity "site:Redmond" -DesignateAsPresenter "Everyone"

</div>

<div>

## <a name="to-change-multiple-property-values-when-creating-meeting-configuration-settings"></a>Per modificare più valori di proprietà durante la creazione delle impostazioni di configurazione delle riunioni

  - Più valori di proprietà possono essere modificati includendo più parametri. Ad esempio, questo comando ammette tutti i partecipanti a una riunione come relatore e costringe anche gli utenti PSTN ad attendere nella sala di attesa finché non vengono formalmente ammessi alla riunione:
    
        New-CsMeetingConfiguration -Identity "site:Redmond" -DesignateAsPresenter "Everyone" -PSTNUCallersBypassLobby $True

</div>

Per altre informazioni, vedere l'argomento della Guida relativo al cmdlet [New-CsMeetingConfiguration](https://technet.microsoft.com/en-us/library/Gg398065(v=OCS.15)) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

