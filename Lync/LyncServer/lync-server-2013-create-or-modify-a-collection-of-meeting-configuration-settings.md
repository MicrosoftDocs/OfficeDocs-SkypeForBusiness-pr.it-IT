---
title: Creare o modificare una raccolta di impostazioni di configurazione delle riunioni
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a collection of meeting configuration settings
ms:assetid: ce6773c1-a0d5-4405-8e32-33a6f3a46a1a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721889(v=OCS.15)
ms:contentKeyID: 49733822
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6906331e8a0b2cf67c8d4c0404caf2816f441ea0
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42151868"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-collection-of-meeting-configuration-settings-in-lync-server-2013"></a>Creare o modificare una raccolta di impostazioni di configurazione delle riunioni in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-02-23_

È possibile utilizzare le impostazioni nella pagina Configurazione riunione per definire diverse caratteristiche di partecipazione alle riunioni. Per impostazione predefinita, le impostazioni globali definiscono la partecipazione alle riunioni. È inoltre possibile creare impostazioni di partecipazione alle riunioni a livello di sito e di pool. Se si creano impostazioni a livello di pool, tali impostazioni si applicheranno a tutte le riunioni ospitate da tale pool. Se invece non si creano impostazioni a livello di pool, si applicheranno le impostazioni a livello di sito, se esistenti. Se non si definiscono impostazioni a livello di sito, le impostazioni globali si applicheranno a tutte le riunioni.

<div>

## <a name="to-create-new-meeting-join-settings"></a>Per creare nuove impostazioni di partecipazione alle riunioni

1.  Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Sulla barra di spostamento sinistra fare clic su **Servizio di conferenza** e quindi su **Configurazione riunione**.

4.  Nella pagina **Configurazione riunione** fare clic su **Nuovo** e quindi eseguire una delle operazioni seguenti:
    
      - Per creare un criterio a livello di sito, fare clic su **Configurazione sito**. Nel campo di ricerca **Seleziona un sito** digitare il nome del sito per cui si desidera definire le impostazioni di partecipazione alle riunioni, per intero o in parte. Fare clic sul sito desiderato nell'elenco dei siti e quindi fare clic su **OK**.
    
      - Per creare un criterio a livello di pool, fare clic su **Configurazione pool**. Nel campo di ricerca **Seleziona un servizio** digitare il nome del pool per cui si desidera definire le impostazioni di partecipazione alle riunioni, per intero o in parte. Fare clic su un pool desiderato nell'elenco di servizi e quindi su **OK**.

5.  Per instradare i partecipanti che accedono dalla rete PSTN (Public Switched Telephone Network ) attraverso la sala di attesa, deselezionare la casella di controllo **I chiamanti PSTN ignorano la sala di attesa**. Per impostazione predefinita, i partecipanti che accedono dalla rete PSTN passano direttamente alla riunione.

6.  Per configurare l'utente che svolge la funzione di relatore nella riunione, in **Designa come relatore** effettuare una delle operazioni seguenti:
    
      - Per non consentire a persone diverse dall'organizzatore di svolgere la funzione di relatore, fare clic su **Nessuno**.
    
      - Per consentire solo ai partecipanti membri dell'organizzazione di svolgere la funzione di relatore, fare clic su **Società**. Questa è l'impostazione predefinita.
    
      - Per consentire a qualsiasi partecipante di fungere da relatore, fare clic su **Tutti**.

7.  Per fare in modo che l'organizzatore selezioni il tipo di conferenza quando pianifica una riunione, deselezionare la casella di controllo **Tipo di conferenza assegnato per impostazione predefinita**. Per impostazione predefinita, il tipo di conferenza viene assegnato automaticamente.

8.  Per impedire che gli utenti anonimi (non autenticati) vengano ammessi automaticamente, deselezionare la casella di controllo **Consenti utenti anonimi per impostazione predefinita**. Per impostazione predefinita, gli utenti anonimi vengono ammessi automaticamente alle riunioni.

9.  Per personalizzare l'invito alla riunione che viene inviato ai partecipanti, eseguire le operazioni seguenti. Si noti che la dimensione massima degli URL e del testo del piè di pagina personalizzato è di 1 KB. Se non si specifica un valore per le personalizzazioni, queste non verranno incluse nella riunione, ad eccezione di **URL Guida**. Se non si include un URL della Guida personalizzato, l'URL della Guida predefinito per Lync verrà visualizzato nell'invito.
    
      - Per personalizzare il logo che viene visualizzato nell'invito alla riunione, immettere il percorso del logo in **URL logo**.
        
        <div>
        

        > [!NOTE]
        > Il logo deve essere un'immagine GIF o JPG con una dimensione di 188 per 30 pixel.

        
        </div>
    
      - Per personalizzare il testo della Guida che viene visualizzato nell'invito alla riunione, immettere il percorso del testo della Guida in **URL Guida**.
    
      - Per personalizzare il testo legale che viene visualizzato nell'invito alla riunione, immettere il percorso del testo legale in **URL testo legale**.
    
      - Per personalizzare il testo del piè di pagina che viene visualizzato nell'invito alla riunione, immettere il testo in **Testo piè di pagina personalizzato**.

10. Fare clic su **Commit**.

</div>

<div>

## <a name="to-modify-an-existing-collection-of-meeting-configurations"></a>Per modificare una raccolta esistente di configurazioni di riunioni

1.  Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Sulla barra di spostamento sinistra fare clic su **Servizio di conferenza** e quindi su **Configurazione riunione**.

4.  Nell'elenco delle configurazioni delle riunioni, fare clic sulla configurazione che si desidera modificare, fare clic su **modifica**e quindi su **Mostra dettagli**.

5.  In **Modifica configurazione riunione** modificare qualsiasi impostazione di configurazione, tranne il nome della configurazione, che non può essere modificato.

6.  Fare clic su **Commit**.

</div>

<div>

## <a name="creating-new-meeting-configuration-settings-by-using-windows-powershell-cmdlets"></a>Creazione di nuove impostazioni di configurazione delle riunioni tramite i cmdlet di Windows PowerShell

È possibile creare le impostazioni di configurazione delle riunioni (solo nell'ambito del sito) utilizzando Windows PowerShell e il cmdlet New-CsMeetingConfiguration. Questo cmdlet può essere eseguito da Lync Server 2013 Management Shell o da una sessione remota di Windows PowerShell. Per informazioni dettagliate sull'utilizzo di Windows PowerShell remoto per la connessione a Lync Server, vedere l'articolo del Blog su Lync Server di Windows PowerShell "Quick Start: Managing Microsoft Lync [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)Server 2010 using Remote PowerShell" at.

<div>

## <a name="to-create-meeting-configuration-settings-that-use-the-default-values"></a>Per creare le impostazioni di configurazione delle riunioni che utilizzano i valori predefiniti

  - Il comando seguente crea un nuovo insieme di impostazioni di configurazione di riunione per il sito Redmond:
    
        New-CsMeetingConfiguration -Identity "site:Redmond"
    
    Poiché nel comando precedente non sono stati specificati parametri, eccetto il parametro obbligatorio Identity, le nuove impostazioni di configurazione di riunione utilizzeranno i valori predefiniti per le relative proprietà.

</div>

<div>

## <a name="to-change-a-property-value-when-creating-meeting-configuration-settings"></a>Per modificare un valore di proprietà durante la creazione delle impostazioni di configurazione delle riunioni

  - Per creare impostazioni basate su valori di proprietà diversi, è sufficiente includere il parametro appropriato e il valore corrispondente. Per creare ad esempio una raccolta di impostazioni di configurazione di riunione che per impostazione predefinita ammettono chiunque come relatore di una riunione, utilizzare un comando simile al seguente:
    
        New-CsMeetingConfiguration -Identity "site:Redmond" -DesignateAsPresenter "Everyone"

</div>

<div>

## <a name="to-change-multiple-property-values-when-creating-meeting-configuration-settings"></a>Per modificare più valori di proprietà durante la creazione di impostazioni di configurazione delle riunioni

  - È possibile modificare più valori di proprietà includendo più parametri. Il comando seguente ad esempio ammette chiunque come relatore di una riunione e forza inoltre il passaggio degli utenti PSTN in una sala di attesa finché non vengono ammessi formalmente alla riunione:
    
        New-CsMeetingConfiguration -Identity "site:Redmond" -DesignateAsPresenter "Everyone" -PSTNUCallersBypassLobby $True

</div>

Per ulteriori informazioni, vedere l'argomento della Guida relativo al cmdlet [New-CsMeetingConfiguration](https://technet.microsoft.com/library/Gg398065(v=OCS.15)) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

