---
title: Configurare il client Skype for business in Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Configure the client experience
ms:assetid: 61e783f1-24f4-430b-ae52-c76a4d206dc7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn954919(v=OCS.15)
ms:contentKeyID: 65227958
ms.date: 09/18/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 20980f0f0b6697eada6c237aa8d2297b0fd227d9
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48503303"
---
# <a name="configure-the-client-experience-with-skype-for-business"></a>Configurare l'esperienza client con Skype for business

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2015-09-17_

**Riepilogo:** In questo argomento viene descritto come configurare l'esperienza client per gli utenti di client Skype for business in un ambiente Lync Server 2013. È possibile configurare l'esperienza client solo se è in esecuzione Lync Server 2013 con l'aggiornamento cumulativo di dicembre 2014 (5.0.8308.857) o versioni successive. Per informazioni sull'aggiornamento di Lync Server 2013, vedere [Updates for Lync server 2013](https://go.microsoft.com/fwlink/p/?linkid=532651).

Skype for business offre una nuova esperienza utente basata sull'esperienza del prodotto consumer Skype. Oltre a tutte le funzionalità di Lync, Skype for business offre nuove funzionalità con controlli semplificati e icone note. Per informazioni dettagliate sulla nuova esperienza client, vedere [Lync è ora Skype for Business--vedere What ' s New](https://go.microsoft.com/fwlink/?linkid=529022).

Lync Server 2013 supporta la nuova esperienza client Skype for business e l'esperienza client Lync. In qualità di amministratore, è possibile scegliere l'esperienza client preferita per gli utenti. Ad esempio, è possibile distribuire l'esperienza client di Lync fino a quando gli utenti dell'organizzazione non sono completamente formati nella nuova esperienza Skype for business. In alternativa, se non sono stati ancora aggiornati tutti gli utenti a Skype for Business Server 2015, è possibile che tutti gli utenti abbiano la stessa esperienza client finché non vengono aggiornati tutti al nuovo server.

<div>


> [!IMPORTANT]  
> Se nell'organizzazione sono stati distribuiti sia Skype for Business Server 2015 che Lync Server 2013, l'esperienza client predefinita diventerà diversa a seconda delle versioni del server e delle impostazioni dell'interfaccia utente. Quando gli utenti lanciano Skype for business per la prima volta, vedranno sempre l'interfaccia utente di Skype for business, anche se è stata selezionata l'interfaccia utente di Lync. Dopo alcuni minuti, agli utenti viene richiesto di passare alla modalità Lync. Per ulteriori informazioni, vedere <STRONG>First Launch client Behavior</STRONG> più avanti in questo argomento.



</div>

<div>


> [!NOTE]  
> L'esperienza client di Lync 2013 non è un'opzione per le versioni client di Skype for business 2016. Prima di tentare di configurare l'ambiente client per l'utilizzo del client Lync 2013, controllare la versione client per verificare che non venga avviata con il numero 16. ad esempio: 16. x.x.x.



</div>

<div>

## <a name="configure-the-client-experience"></a>Configurare l'esperienza client

È possibile specificare l'esperienza client che gli utenti dell'organizzazione vedranno utilizzando il cmdlet **Set-CsClientPolicy** con il parametro EnableSkypeUI. Il comando seguente consente di selezionare l'esperienza client Skype for business per tutti gli utenti dell'organizzazione a cui è applicato il criterio globale (ricordarsi, il sito o i criteri specifici dell'utente eseguono l'override del criterio globale):

    Set-CsClientPolicy -Identity Global -EnableSkypeUI $true

Il comando seguente consente di selezionare l'esperienza client di Lync per tutti gli utenti dell'organizzazione coinvolti nei criteri globali:

    Set-CsClientPolicy -Identity Global -EnableSkypeUI $false

Il comando seguente consente di selezionare l'esperienza client Skype for business per tutti gli utenti all'interno del sito Redmond:

    Set-CsClientPolicy -Identity site:Redmond -EnableSkypeUI $true

Se si desidera configurare l'esperienza client per utenti specifici all'interno dell'organizzazione, è possibile creare un nuovo criterio utente utilizzando il cmdlet **New-CsClientPolicy** e quindi assegnare il criterio a utenti specifici utilizzando il cmdlet **Grant-CsClientPolicy** .

Ad esempio, il comando seguente consente di creare un nuovo criterio client, SalesClientUI, che seleziona l'esperienza client Skype for business:

    New-CsClientPolicy -Identity SalesClientUI -EnableSkypeUI $true

Il comando seguente assegna il criterio, SalesClientUI, a tutti i membri del reparto vendite:

    Get-CsUser -LDAPFilter "Department=Sales" | Grant-CsClientPolicy -PolicyName SalesClientUI

</div>

<div>

## <a name="first-launch-client-behaviors"></a>Primo avvio di comportamenti client

Per impostazione predefinita, quando gli utenti avviano Skype for business per la prima volta, vedranno sempre l'interfaccia utente di Skype for business, anche se è stata selezionata l'esperienza client di Lync impostando il valore del parametro EnableSkypeUI su $False come descritto in precedenza. Dopo alcuni minuti, agli utenti verrà richiesto di passare alla modalità Lync.

Se si desidera visualizzare l'interfaccia utente di Lync quando gli utenti avviano il client Skype for business per la prima volta, attenersi alla seguente procedura prima che il client venga avviato per la prima volta dopo essere stato aggiornato:

1.  Verificare che il valore di `EnableSkypeUI` sia impostato su $false nel criterio che si sta utilizzando come descritto in precedenza.

2.  Aggiornare il registro di sistema nel computer dell'utente. Si consiglia di eseguire questa operazione prima che gli utenti avviino il client Skype for business ed è necessario eseguire questa operazione una sola volta. Per informazioni su come creare un oggetto Criteri di gruppo per aggiornare il registro di sistema in un computer aggiunto a un dominio, vedere la sezione più avanti nell'argomento.
    
    Nella chiave ** \[ \_ \_ \\ \\ Microsoft \\ Office \\ Lync \] del software utente corrente di HKEY** creare un nuovo valore **binario** .
    
    Il **nome del valore** deve essere **EnableSkypeUI**e i **dati del valore** devono essere impostati su **00 00 00 00**.
    
    La chiave dovrebbe essere simile alla seguente:
    
        [HKEY_CURRENT_USER\Software\Microsoft\Office\Lync]
        "CanSharePptInCollab"=dword:00000001
        "CanShareOneNoteInCollab"=dword:00000001
        "CanAppShareInCollab"=dword:00000001
        "EnableSkypeUI"=hex:00,00,00,00

L'interfaccia utente di Lync verrà visualizzata quando gli utenti avviano il client Skype for business per la prima volta.

<div>

## <a name="control-the-display-of-the-welcome-screen-tutorial"></a>Controllare la visualizzazione dell'esercitazione sulla schermata iniziale

Quando gli utenti aprono il client Skype for business, il comportamento predefinito consiste nel visualizzare una schermata di benvenuto che include *7 suggerimenti rapidi che la maggior parte delle persone richiede*. È possibile disattivare la visualizzazione della schermata iniziale ma consentire comunque agli utenti di accedere all'esercitazione aggiungendo il seguente valore del registro di sistema nel computer client:

Nella chiave ** \[ \_ \_ \\ \\ Microsoft \\ Office \\ 15,0 \\ Lync \] del software utente corrente di HKEY** creare un nuovo **valore DWORD (32 bit)**. Il **nome del valore** deve essere **IsBasicTutorialSeenByUser**e i **dati del valore** devono essere impostati su **1**.

La chiave dovrebbe essere simile alla seguente:

    "IsBasicTutorialSeenByUser"=dword:00000001

</div>

<div>

## <a name="turn-off-the-client-tutorial"></a>Disattivare l'esercitazione del client

Se non si desidera che gli utenti siano in grado di accedere all'esercitazione, è possibile disattivare l'esercitazione client con il seguente valore del registro di sistema:

Nella chiave ** \[ \_ \_ \\ \\ Microsoft \\ Office \\ 15,0 \\ Lync \] del software utente corrente di HKEY** creare un nuovo **valore DWORD (32 bit)**. Il **nome del valore** deve essere **TutorialFeatureEnabled**e i **dati del valore** devono essere impostati su **0**.

    "TutorialFeatureEnabled"=dword:00000000

È possibile riattivare l'esercitazione impostando i **dati di valore** su **1**.

</div>

</div>

<div>

## <a name="default-client-experiences"></a>Esperienze client predefinite

Se l'organizzazione dispone sia di Skype for Business Server 2015 che di Lync Server distribuiti, l'esperienza client diventerà diversa a seconda delle versioni del server e dell'impostazione dell'interfaccia utente di Skype. Nella tabella seguente viene illustrata l'esperienza client iniziale in base alla versione del server e all'impostazione dell'interfaccia utente:


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Versione server</p></th>
<th><p>Impostazione di EnableSkypeUI</p></th>
<th><p>Esperienza client</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Skype for Business Server 2015</p></td>
<td><p>Predefiniti</p></td>
<td><p>Skype for Business</p></td>
</tr>
<tr class="even">
<td><p>Skype for Business Server 2015</p></td>
<td><p>Vero</p></td>
<td><p>Skype for Business</p></td>
</tr>
<tr class="odd">
<td><p>Skype for Business Server 2015</p></td>
<td><p>False</p></td>
<td><p>L'utente ha chiesto di passare alla modalità Lync (l'utente può passare a Skype for business in un secondo momento se si modifica l'impostazione dell'interfaccia utente in $true)</p></td>
</tr>
<tr class="even">
<td><p>Lync Server 2010 o Lync Server 2013 (con le patch corrette)</p></td>
<td><p>Predefiniti</p></td>
<td><p>L'utente ha chiesto di passare alla modalità Lync (l'utente può passare a Skype for business in un secondo momento se si modifica l'impostazione dell'interfaccia utente in $true)</p></td>
</tr>
<tr class="odd">
<td><p>Lync Server 2010 o Lync Server 2013 (con le patch corrette)</p></td>
<td><p>Vero</p></td>
<td><p>Skype for Business</p></td>
</tr>
<tr class="even">
<td><p>Lync Server 2010 o Lync Server 2013 (con le patch corrette)</p></td>
<td><p>False</p></td>
<td><p>L'utente ha chiesto di passare alla modalità Lync (l'utente può passare a Skype for business in un secondo momento se si modifica l'impostazione dell'interfaccia utente in $true)</p></td>
</tr>
<tr class="odd">
<td><p>Lync Server 2010 o Lync Server 2013 (senza patch)</p></td>
<td><p>Predefiniti</p></td>
<td><p>L'utente ha chiesto di passare a Lync Client Experience (l'utente non può passare a Skype for business in un secondo momento)</p></td>
</tr>
</tbody>
</table>


La tabella successiva Visualizza l'esperienza client quando l'amministratore cambia l'impostazione iniziale per l'esperienza dell'interfaccia utente di Skype:


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Versione server</p></th>
<th><p>Impostazione dell'interfaccia utente di Skype</p></th>
<th><p>Client UI = Lync</p></th>
<th><p>Client UI = Skype for business</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Skype for Business Server 2015</p></td>
<td><p>Vero</p></td>
<td><p>L'utente ha chiesto di passare a Skype for business</p></td>
<td><p>Skype for Business</p></td>
</tr>
<tr class="even">
<td><p>Skype for Business Server 2015</p></td>
<td><p>False</p></td>
<td><p>Interfaccia utente di Lync</p></td>
<td><p>L'utente ha chiesto di passare all'interfaccia utente di Lync</p></td>
</tr>
<tr class="odd">
<td><p>Lync Server 2010 o Lync Server 2013 (con le patch corrette)</p></td>
<td><p>Vero</p></td>
<td><p>L'utente ha chiesto di passare a Skype for business</p></td>
<td><p>Skype for Business</p></td>
</tr>
<tr class="even">
<td><p>Lync Server 2010 o Lync Server 2013 (con le patch corrette)</p></td>
<td><p>False</p></td>
<td><p>Interfaccia utente di Lync</p></td>
<td><p>L'utente ha chiesto di passare all'interfaccia utente di Lync</p></td>
</tr>
<tr class="odd">
<td><p>Lync Server 2010 o Lync Server 2013 (senza patch)</p></td>
<td><p>Predefiniti</p></td>
<td><p>Modalità Lync (non è possibile passare a Skype for business)</p></td>
<td><p>Lync UI (non è possibile passare a Skype for business)</p></td>
</tr>
</tbody>
</table>


Le versioni delle patch necessarie per gestire la configurazione del client Skype for business sono le seguenti:

  - Lync Server 2010-February 2015 Cumulative Update (4.0.7577.710) per Lync Server 2010. Per informazioni, vedere [Updates for Lync Server 2010](https://go.microsoft.com/fwlink/p/?linkid=532771)

  - Lync Server 2013-dicembre 2014 Cumulative Update (5.0.8308.857) per Lync Server 2013. Per informazioni, vedere [Updates for Lync Server 2013](https://go.microsoft.com/fwlink/p/?linkid=532772).

</div>

<div>

## <a name="create-a-group-policy-object-to-modify-the-registry-on-a-domain-joined-computer"></a>Creare un oggetto Criteri di gruppo per modificare il registro di sistema in un computer aggiunto a un dominio

L'aggiornamento del registro di sistema per la visualizzazione dell'esperienza client di Lync al primo avvio del client Skype for business deve essere eseguito una sola volta. Se si utilizza un oggetto Criteri di gruppo per aggiornare il registro di sistema, è necessario definire l'oggetto per creare un nuovo valore anziché aggiornare i dati del valore. Quando viene applicato l'oggetto Criteri di gruppo, se il nuovo valore non esiste, verrà creato dal GPO e i dati del valore verranno impostati su 0.

Nella procedura seguente viene descritto come modificare il registro di sistema in modo che l'esperienza client di Lync venga visualizzata al primo avvio di Skype for business da parte di un utente. È inoltre possibile utilizzare questa procedura per aggiornare il registro di sistema per disabilitare l'esercitazione introduttiva sulla schermata come descritto in precedenza.

**Per creare l'oggetto Criteri di gruppo**

1.  Avviare la **console di gestione di criteri di gruppo**.
    
    Per informazioni su come utilizzare la console Gestione criteri di gruppo, vedere [Group Policy Management Console](https://go.microsoft.com/fwlink/?linkid=532759).

2.  Fare clic con il pulsante destro del mouse sul nodo **oggetti Criteri di gruppo** e scegliere **nuovo** dal menu.

3.  Nella finestra di dialogo **nuovo oggetto Criteri** di gruppo immettere un nome per l'oggetto Criteri di gruppo, ad esempio **MakeLyncDefaultUI**, e quindi fare clic su **OK**.

4.  Fare clic con il pulsante destro del mouse sul nuovo oggetto Criteri di gruppo appena creato e quindi scegliere **modifica** dal menu.

5.  In **Editor gestione criteri di gruppo**espandere **Configurazione utente**, espandere **Preferenze**, espandere **impostazioni di Windows**e quindi selezionare il nodo **del registro di sistema** .

6.  Fare clic con il pulsante destro del mouse sul nodo **del registro di sistema** e scegliere **nuovo** \> **elemento del registro di sistema**.

7.  Nella finestra di dialogo **nuove proprietà del registro di sistema** , aggiornare quanto segue:
    
    
    <table>
    <colgroup>
    <col style="width: 50%" />
    <col style="width: 50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th>Campo</th>
    <th>Valore da selezionare o immettere</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><strong>Azione</strong></p></td>
    <td><p><strong>Creare</strong></p></td>
    </tr>
    <tr class="even">
    <td><p><strong>Alveare</strong></p></td>
    <td><p>HKEY_CURRENT_USER</p></td>
    </tr>
    <tr class="odd">
    <td><p><strong>Percorso chiave</strong></p></td>
    <td><p>Software\Microsoft\Office\Lync</p></td>
    </tr>
    <tr class="even">
    <td><p><strong>Nome valore</strong></p></td>
    <td><p>EnableSkypeUI</p></td>
    </tr>
    <tr class="odd">
    <td><p><strong>Tipo valore</strong></p></td>
    <td><p>REG_BINARY</p></td>
    </tr>
    <tr class="even">
    <td><p><strong>Value data</strong></p></td>
    <td><p>00000000</p></td>
    </tr>
    </tbody>
    </table>


8.  Fare clic su **OK** per salvare le modifiche e quindi chiudere l'oggetto Criteri di gruppo.

Successivamente, è necessario collegare l'oggetto Criteri di gruppo creato all'insieme di utenti a cui si desidera assegnare il criterio, ad esempio un'unità organizzativa.

**Per utilizzare l'oggetto Criteri di gruppo per assegnare il criterio**

1.  Nella console Gestione criteri di gruppo fare clic con il pulsante destro del mouse sull'unità organizzativa a cui si desidera assegnare il criterio e quindi scegliere **collegamento a un oggetto Criteri**di sistema esistente.

2.  Nella finestra di dialogo **Seleziona oggetto Criteri** di gruppo selezionare l'oggetto Criteri di gruppo creato e quindi fare clic su **OK**.

3.  Nel computer dell'utente di destinazione aprire una finestra del prompt dei comandi e digitare il comando seguente:
    
    **gpupdate/target: utente**
    
    Il messaggio "aggiornamento dei criteri..." viene visualizzato quando viene applicato l'oggetto Criteri di gruppo. Al termine dell'operazione, viene visualizzato il messaggio "aggiornamento dei criteri utente completato".

4.  Al prompt dei comandi, digitare il seguente comando:
    
    **gpresult/r**
    
    Dovrebbe essere visualizzato "oggetti Criteri di gruppo assegnati" con il nome del GPO creato in basso.

È inoltre possibile verificare che l'oggetto Criteri di gruppo abbia aggiornato correttamente il registro di sistema nel computer di un utente esaminando il registro di sistema. Aprire l'editor del registro di sistema e passare alla chiave di ** \[ \_ \_ \\ \\ Microsoft \\ Office \\ \] Lync del software utente corrente di HKEY** . Se l'oggetto Criteri di gruppo ha aggiornato correttamente il registro di sistema, verrà visualizzato un valore denominato EnableSkypeUI con un valore pari a 0.

</div>

</div>

<span> </span>

</div>

</div>

</div>

