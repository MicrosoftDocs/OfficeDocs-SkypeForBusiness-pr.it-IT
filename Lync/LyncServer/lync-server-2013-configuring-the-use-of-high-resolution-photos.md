---
title: "Lync Server 2013: configurazione dell'uso di foto ad alta risoluzione"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring the use of high-resolution photos in Lync Server 2013
ms:assetid: 995da78a-dc44-45a3-908d-16fe36cfa0d9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688150(v=OCS.15)
ms:contentKeyID: 49733753
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5cb82c047491a43f2a8682d3a6688f67e76af730
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41734606"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-the-use-of-high-resolution-photos-in-microsoft-lync-server-2013"></a>Configurazione dell'uso di foto ad alta risoluzione in Microsoft Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2014-02-05_

Microsoft Lync Server 2010 ha fornito agli utenti la possibilità di visualizzare le foto dei loro contatti (e di rendere le proprie foto disponibili per gli altri). In genere queste foto sono state archiviate come parte dell'attributo thumbnailPhoto dell'utente in Active Directory. Questo ha posto un grave limite alle dimensioni e alla risoluzione delle Foto: l'attributo thumbnailPhoto può contenere solo una fotografia con una dimensione massima di 48 pixel per 48 pixel.

In Microsoft Lync Server 2013, tuttavia, le foto possono essere archiviate nella cassetta postale di Microsoft Exchange Server 2013 di un utente. che consente di ridimensionare le foto fino a 648 pixel per 648 pixel. Oltre a questo, Exchange 2013 può ridimensionare automaticamente queste foto per l'uso in prodotti diversi in base alle esigenze. In genere significa tre diverse dimensioni e risoluzioni delle Foto:

  - 48 pixel per 48 pixel, le dimensioni usate per l'attributo thumbnailPhoto di Active Directory. Se si carica una foto in Exchange 2013 Exchange creerà automaticamente una versione di 48 pixel per 48 pixel della foto e aggiornerà l'attributo thumbnailPhoto dell'utente. Si noti tuttavia che il contrario non è vero: se si aggiorna manualmente l'attributo thumbnailPhoto in Active Directory, la foto nella cassetta postale di Exchange 2013 dell'utente non verrà aggiornata automaticamente.

  - 96 pixel per 96 pixel, per l'uso in Microsoft Outlook 2013 Web App, Microsoft Outlook 2013, Microsoft Lync Web App e Lync 2013.

  - 648 pixel per 648 pixel per l'uso in Lync 2013 e in Microsoft Lync Web App.

<div>


> [!NOTE]  
> Se si hanno le risorse, è consigliabile caricare le foto di 648x648; che offre la massima risoluzione e una qualità ottimale delle immagini in tutte le applicazioni di Office 2013. Ogni foto JPEG con una dimensione di 648x648 e una profondità di 24 bit genera una dimensione del file di circa 240 kilobyte. Questo significa che avrai bisogno di circa 1 megabyte di spazio su disco per ogni 4 foto utente.



</div>

Le foto ad alta risoluzione, a cui si accede usando i servizi Web di Exchange, possono essere caricate dagli utenti che usano Outlook 2013 Web App; agli utenti è consentito aggiornare solo la propria foto. Gli amministratori possono tuttavia aggiornare la foto per qualsiasi utente usando Exchange Management Shell e una serie di comandi di Windows PowerShell simili ai seguenti:

    $photo = ([Byte[]] $(Get-Content -Path "C:\Photos\Kenmyer.jpg" -Encoding Byte -ReadCount 0))
    Set-UserPhoto -Identity "Ken Myer" -PictureData $photo -Confirm:$False
    Set-UserPhoto -Identity "Ken Myer" -Save -Confirm:$False

Il primo comando nell'esempio precedente usa il cmdlet Get-Content per leggere il contenuto del file C:\\Photos\\kenmyer. jpg e archiviare i dati in una variabile denominata $Photo. Nel secondo comando viene usato il cmdlet Set-UserPhoto di Exchange per caricare la foto e allegare la foto all'account utente di Ken.

<div>


> [!NOTE]  
> In questo esempio, il nome visualizzato in Active Directory di Ken è usato come identità dell'account utente. È anche possibile fare riferimento a un account utente usando altri identificatori, ad esempio l'indirizzo SMTP dell'utente o il nome dell'entità utente. <A href="http://go.microsoft.com/fwlink/p/?linkid=268536">http://go.microsoft.com/fwlink/p/?LinkId=268536</A> Per altre informazioni, vedere la documentazione relativa al cmdlet Set-UserPhoto.



</div>

Il caricamento della foto non equivale all'assegnazione di tale foto all'account utente di Ken. Invece, il caricamento della foto restituisce semplicemente un'anteprima della foto da visualizzare nella pagina delle opzioni di Outlook Web App. Per assegnare effettivamente la foto all'account utente, l'utente deve fare clic su **Salva** nella pagina Opzioni oppure l'amministratore deve eseguire il terzo comando nell'esempio. Questo terzo comando usa il parametro Save per assegnare la foto all'account utente di Ken requestro:

    Set-UserPhoto -Identity "Ken Myer" -Save -Confirm:$False

Per verificare che la nuova foto sia stata assegnata all'account utente, Ken può accedere a Lync 2013, selezionare **Opzioni**e quindi selezionare **immagine personale**. La foto appena caricata deve essere visualizzata come foto personale di Ken. In alternativa, gli amministratori possono verificare la foto per qualsiasi utente avviando Internet Explorer e passando a un URL simile al seguente:

    https://atl-mail-001.litwareinc.com/ews/Exchange.asmx/s/GetUserPhoto?email=kenmyer@litwareinc.com&size=HR648x648

Se l'amministratore può visualizzare la foto con Internet Explorer, ma l'utente non può visualizzare la propria foto in Lync 2013, che in genere indica un problema di connettività con i servizi Web di Exchange o con il servizio di individuazione automatica di Exchange.

Tieni presente che non è richiesta alcuna configurazione aggiuntiva per rendere disponibile questa foto in Lync 2013. La foto sarà invece immediatamente disponibile dopo che è stata caricata e il cmdlet Set-UserPhoto è stato eseguito.

</div>

<span> </span>

</div>

</div>

</div>

