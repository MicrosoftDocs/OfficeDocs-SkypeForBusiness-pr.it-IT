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
ms.openlocfilehash: 1e1aa407fbb1d7d8a006698d30545165352386b1
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41729036"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-the-client-experience-with-skype-for-business"></a>Configurare l'esperienza client con Skype for Business

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2015-09-17_

**Riepilogo:** Questo argomento descrive come configurare l'esperienza client per gli utenti del client Skype for business in un ambiente Lync Server 2013. È possibile configurare l'esperienza client solo se è in uso Lync Server 2013 con l'aggiornamento cumulativo di dicembre 2014 (5.0.8308.857) o versione successiva installata. Per informazioni sull'aggiornamento di Lync Server 2013, vedere [aggiornamenti per Lync server 2013](http://go.microsoft.com/fwlink/p/?linkid=532651).

Skype for business offre una nuova esperienza utente basata sull'esperienza di prodotto consumer Skype. Oltre a tutte le funzionalità di Lync, Skype for business offre nuove funzionalità con controlli semplificati e icone note. Per informazioni dettagliate sulla nuova esperienza client, vedere [Lync è ora Skype for business-](http://go.microsoft.com/fwlink/?linkid=529022)Ecco le novità.

Lync Server 2013 supporta la nuova esperienza client Skype for business e l'esperienza client Lync. Come amministratore, puoi scegliere l'esperienza client preferita per gli utenti. Ad esempio, potresti voler distribuire l'esperienza del client Lync fino a quando gli utenti dell'organizzazione non saranno completamente formati nella nuova esperienza di Skype for business. In alternativa, se non sono stati ancora aggiornati tutti gli utenti a Skype for Business Server 2015, è possibile che tutti gli utenti abbiano la stessa esperienza client fino a quando tutti vengono aggiornati nel nuovo server.

<div>


> [!IMPORTANT]  
> Se l'organizzazione ha installato sia Skype for Business Server 2015 che Lync Server 2013, l'esperienza client predefinita sarà diversa a seconda delle versioni del server e delle impostazioni dell'interfaccia utente. Quando gli utenti avviano Skype for business per la prima volta, vedranno sempre l'interfaccia utente di Skype for business, anche se è stata selezionata l'interfaccia utente di Lync. Dopo alcuni minuti, agli utenti viene chiesto di passare alla modalità Lync. Per altre informazioni, vedere <STRONG>prima</STRONG> di tutto avviare il comportamento del client più avanti in questo argomento.



</div>

<div>


> [!NOTE]  
> L'esperienza client di Lync 2013 non è un'opzione per le versioni client di Skype for business 2016. Prima di provare a configurare l'ambiente client per l'utilizzo del client Lync 2013, verifica che la versione client non inizi con il numero 16; ad esempio: 16.x.x.x.



</div>

<div>

## <a name="configure-the-client-experience"></a>Configurare l'esperienza client

Puoi specificare l'esperienza client che gli utenti dell'organizzazione vedranno usando il cmdlet **Set-CsClientPolicy** con il parametro EnableSkypeUI. Il comando seguente seleziona l'esperienza del client Skype for business per tutti gli utenti dell'organizzazione interessati dal criterio globale (Ricordati che i criteri per il sito o i criteri specifici dell'utente sostituiscono il criterio globale):

    Set-CsClientPolicy -Identity Global -EnableSkypeUI $true

Il comando successivo seleziona l'esperienza client Lync per tutti gli utenti dell'organizzazione interessati dal criterio globale:

    Set-CsClientPolicy -Identity Global -EnableSkypeUI $false

Il comando successivo seleziona l'esperienza client Skype for business per tutti gli utenti all'interno del sito Redmond:

    Set-CsClientPolicy -Identity site:Redmond -EnableSkypeUI $true

Se si vuole configurare l'esperienza client per utenti specifici all'interno dell'organizzazione, è possibile creare un nuovo criterio utente usando il cmdlet **New-CsClientPolicy** e quindi assegnare il criterio a utenti specifici usando il cmdlet **Grant-CsClientPolicy** .

Ad esempio, il comando seguente crea un nuovo criterio client, SalesClientUI, che seleziona l'esperienza del client Skype for business:

    New-CsClientPolicy -Identity SalesClientUI -EnableSkypeUI $true

Il comando successivo assegna il criterio SalesClientUI a tutti i membri del reparto vendite:

    Get-CsUser -LDAPFilter "Department=Sales" | Grant-CsClientPolicy -PolicyName SalesClientUI

</div>

<div>

## <a name="first-launch-client-behaviors"></a>Comportamenti del client al primo avvio

Per impostazione predefinita, quando gli utenti avviano Skype for business per la prima volta, vedranno sempre l'interfaccia utente di Skype for business, anche se hai selezionato l'esperienza client di Lync impostando il valore del parametro EnableSkypeUI su $False come descritto in precedenza. . Dopo alcuni minuti, all'utente verrà richiesto di passare alla modalità Lync.

Se desideri visualizzare l'interfaccia utente di Lync al primo avvio del client Skype for Business da parte dell'utente, segui questa procedura prima che il client venga avviato per la prima volta in seguito all'aggiornamento:

1.  Verificare che il valore di `EnableSkypeUI` sia impostato su $false nel criterio in uso come descritto in precedenza.

2.  Aggiorna il Registro di sistema nel computer dell'utente. Esegui l'operazione una sola volta, prima del primo avvio del client Skype for Business da parte dell'utente. Per informazioni su come creare un oggetto Criteri di gruppo per aggiornare il Registro di sistema in un computer che fa parte di un dominio, vedi la sezione presente successivamente nell'argomento.
    
    Nella chiave ** \[Microsoft\_\\Office\\Lync\\\] del\\software utente\_corrente di HKEY** creare un nuovo valore **binario** .
    
    **Nome valore** deve essere **EnableSkypeUI**, mentre **Dati valore** deve essere impostato su **00 00 00 00**.
    
    La chiave dovrebbe avere un aspetto simile al seguente:
    
        [HKEY_CURRENT_USER\Software\Microsoft\Office\Lync]
        "CanSharePptInCollab"=dword:00000001
        "CanShareOneNoteInCollab"=dword:00000001
        "CanAppShareInCollab"=dword:00000001
        "EnableSkypeUI"=hex:00,00,00,00

L'interfaccia utente di Lync verrà visualizzata al primo avvio del client Skype for Business da parte dell'utente.

<div>

## <a name="control-the-display-of-the-welcome-screen-tutorial"></a>Controllare la visualizzazione dell'esercitazione nella schermata iniziale

Quando gli utenti aprono il client Skype for business, il comportamento predefinito prevede la visualizzazione di una schermata iniziale che include *7 suggerimenti veloci che la maggior parte delle persone richiede*. Puoi disattivare la visualizzazione della schermata iniziale ma consentire comunque agli utenti di accedere all'esercitazione aggiungendo il seguente valore del Registro di sistema nel computer client:

Nella ** \[HKEY\_corrente\_del\\software\\Microsoft\\Office\\15,0\\Lync\] ** Key creare un nuovo **valore DWORD (32 bit)**. **Nome valore** deve essere **IsBasicTutorialSeenByUser**, mentre **Dati valore** deve essere impostato su **1**.

La chiave dovrebbe avere un aspetto simile al seguente:

    "IsBasicTutorialSeenByUser"=dword:00000001

</div>

<div>

## <a name="turn-off-the-client-tutorial"></a>Disattivare l'esercitazione nel client

Se non vuoi che gli utenti siano in grado di accedere all'esercitazione, puoi disattivare l'esercitazione nel client con il seguente valore del Registro di sistema:

Nella ** \[HKEY\_corrente\_del\\software\\Microsoft\\Office\\15,0\\Lync\] ** Key creare un nuovo **valore DWORD (32 bit)**. **Nome valore** deve essere **TutorialFeatureEnabled**, mentre **Dati valore** deve essere impostato su **0**.

    "TutorialFeatureEnabled"=dword:00000000

Puoi riattivare l'esercitazione impostando **Dati valore** su **1**.

</div>

</div>

<div>

## <a name="default-client-experiences"></a>Esperienze client predefinite

Se l'organizzazione ha installato sia Skype for Business Server 2015 che Lync Server, l'esperienza del client sarà diversa a seconda delle versioni del server e dell'impostazione dell'interfaccia utente Skype. La tabella seguente mostra l'esperienza client iniziale in base alla versione del server e all'impostazione dell'interfaccia utente:


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Versione del server</p></th>
<th><p>Impostazione EnableSkypeUI</p></th>
<th><p>Esperienza client</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Skype for Business Server 2015</p></td>
<td><p>Predefinita</p></td>
<td><p>Skype for business</p></td>
</tr>
<tr class="even">
<td><p>Skype for Business Server 2015</p></td>
<td><p>True</p></td>
<td><p>Skype for business</p></td>
</tr>
<tr class="odd">
<td><p>Skype for Business Server 2015</p></td>
<td><p>False</p></td>
<td><p>L'utente ha chiesto di passare alla modalità Lync (l'utente può passare a Skype for business in un secondo momento se si modifica l'impostazione dell'interfaccia utente in $true)</p></td>
</tr>
<tr class="even">
<td><p>Lync Server 2010 o Lync Server 2013 (con le patch corrette)</p></td>
<td><p>Predefinita</p></td>
<td><p>L'utente ha chiesto di passare alla modalità Lync (l'utente può passare a Skype for business in un secondo momento se si modifica l'impostazione dell'interfaccia utente in $true)</p></td>
</tr>
<tr class="odd">
<td><p>Lync Server 2010 o Lync Server 2013 (con le patch corrette)</p></td>
<td><p>True</p></td>
<td><p>Skype for business</p></td>
</tr>
<tr class="even">
<td><p>Lync Server 2010 o Lync Server 2013 (con le patch corrette)</p></td>
<td><p>False</p></td>
<td><p>L'utente ha chiesto di passare alla modalità Lync (l'utente può passare a Skype for business in un secondo momento se si modifica l'impostazione dell'interfaccia utente in $true)</p></td>
</tr>
<tr class="odd">
<td><p>Lync Server 2010 o Lync Server 2013 (senza patch)</p></td>
<td><p>Predefinita</p></td>
<td><p>L'utente ha chiesto di passare all'esperienza client Lync (l'utente non può passare a Skype for business in seguito)</p></td>
</tr>
</tbody>
</table>


La tabella seguente mostra l'esperienza del client quando l'amministratore cambia l'impostazione iniziale per l'esperienza dell'interfaccia utente di Skype:


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Versione del server</p></th>
<th><p>Impostazione dell'interfaccia utente Skype</p></th>
<th><p>Interfaccia utente client = Lync</p></th>
<th><p>Interfaccia utente client = Skype for business</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Skype for Business Server 2015</p></td>
<td><p>True</p></td>
<td><p>L'utente ha chiesto di passare a Skype for business</p></td>
<td><p>Skype for business</p></td>
</tr>
<tr class="even">
<td><p>Skype for Business Server 2015</p></td>
<td><p>False</p></td>
<td><p>Interfaccia utente di Lync</p></td>
<td><p>L'utente ha chiesto di passare all'interfaccia utente di Lync</p></td>
</tr>
<tr class="odd">
<td><p>Lync Server 2010 o Lync Server 2013 (con le patch corrette)</p></td>
<td><p>True</p></td>
<td><p>L'utente ha chiesto di passare a Skype for business</p></td>
<td><p>Skype for business</p></td>
</tr>
<tr class="even">
<td><p>Lync Server 2010 o Lync Server 2013 (con le patch corrette)</p></td>
<td><p>False</p></td>
<td><p>Interfaccia utente di Lync</p></td>
<td><p>L'utente ha chiesto di passare all'interfaccia utente di Lync</p></td>
</tr>
<tr class="odd">
<td><p>Lync Server 2010 o Lync Server 2013 (senza patch)</p></td>
<td><p>Predefinita</p></td>
<td><p>Modalità Lync (non è possibile passare a Skype for business)</p></td>
<td><p>Interfaccia utente di Lync (non è possibile passare a Skype for business)</p></td>
</tr>
</tbody>
</table>


Le versioni di patch necessarie per gestire la configurazione del client Skype for business sono:

  - Lync Server 2010-aggiornamento cumulativo di febbraio 2015 (4.0.7577.710) per Lync Server 2010. Per informazioni, vedere [aggiornamenti per Lync Server 2010](http://go.microsoft.com/fwlink/p/?linkid=532771)

  - Lync Server 2013-aggiornamento cumulativo di dicembre 2014 (5.0.8308.857) per Lync Server 2013. Per informazioni, vedere [aggiornamenti per Lync Server 2013](http://go.microsoft.com/fwlink/p/?linkid=532772).

</div>

<div>

## <a name="create-a-group-policy-object-to-modify-the-registry-on-a-domain-joined-computer"></a>Creare un oggetto Criteri di gruppo per modificare il Registro di sistema in un computer che fa parte di un dominio

L'aggiornamento del Registro di sistema per la visualizzazione dell'esperienza client Lync al primo avvio del client Skype for Business da parte dell'utente deve essere eseguito una sola volta. Se usi un oggetto Criteri di gruppo per aggiornare il Registro di sistema, devi definire l'oggetto per creare un nuovo valore anziché aggiornare Dati valore. Quando viene applicato l'oggetto Criteri di gruppo, se il nuovo valore non esiste, l'oggetto Criteri di gruppo lo creerà e imposterà Dati valore su 0.

Nella seguente procedura viene illustrato come modificare il Registro di sistema in modo che l'esperienza client Lync venga visualizzata al primo avvio del client Skype for Business da parte dell'utente. Puoi inoltre utilizzare questa procedura per aggiornare il Registro di sistema e disabilitare l'esercitazione nella schermata iniziale come descritto in precedenza.

**Per creare il GPO**

1.  Avvia la **Console Gestione Criteri di gruppo**.
    
    Per informazioni su come usare la Console Gestione Criteri di gruppo, vedi [Console Gestione Criteri di gruppo](http://go.microsoft.com/fwlink/?linkid=532759).

2.  Fai clic con il pulsante destro del mouse sul nodo **Oggetti Criteri di gruppo** e seleziona **Nuovo** nel menu.

3.  Nella finestra di dialogo **nuovo GPO** immettere un nome per il GPO, ad esempio **MakeLyncDefaultUI**, quindi fare clic su **OK**.

4.  Fai clic con il pulsante destro del mouse sul nuovo oggetto Criteri di gruppo creato, quindi seleziona **Modifica** dal menu.

5.  Nella finestra **Editor Gestione Criteri di gruppo** espandi **Configurazione utente**, espandi **Preferenze**, quindi **Impostazioni di Windows** e seleziona il nodo **Registro di sistema**.

6.  Fare clic con il pulsante destro del mouse sul nodo del **Registro di sistema** e scegliere **nuova** \> **voce del registro di sistema**.

7.  Nella finestra di dialogo **Nuove proprietà Registro di sistema** aggiorna i seguenti elementi:
    
    
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
    <td><p><strong>Create</strong></p></td>
    </tr>
    <tr class="even">
    <td><p><strong>Hive</strong></p></td>
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
    <td><p><strong>Dati valore</strong></p></td>
    <td><p>00000000</p></td>
    </tr>
    </tbody>
    </table>


8.  Fai clic su **OK** per salvare le modifiche e quindi chiudi l'oggetto Criteri di gruppo.

Successivamente dovrai collegare l'oggetto Criteri di gruppo creato al gruppo di utenti a cui vuoi assegnare il criterio, ad esempio un'unità organizzativa.

**Per usare il GPO per assegnare il criterio**

1.  In Console Gestione Criteri di gruppo fai clic con il pulsante destro del mouse sull'unità organizzativa a cui vuoi assegnare il criterio e quindi seleziona **Collega a un oggetto Criteri di gruppo esistente**.

2.  Nella finestra di dialogo **Seleziona oggetto Criteri di gruppo** seleziona l'oggetto Criteri di gruppo creato, quindi seleziona **OK**.

3.  Nel computer dell'utente di destinazione apri un prompt dei comandi e digita il seguente comando:
    
    **gpupdate /target:user**
    
    Durante l'applicazione dell'oggetto Criteri di gruppo verrà visualizzato il messaggio "Aggiornamento criteri in corso...". Al termine dell'operazione verrà visualizzato il messaggio "Aggiornamento dei criteri utente completato".

4.  Al prompt dei comandi digita il seguente comando:
    
    **gpresult /r**
    
    Di seguito dovresti visualizzare "Oggetti Criteri di gruppo assegnati" con il nome dell'oggetto Criteri di gruppo creato.

Puoi inoltre verificare che l'oggetto Criteri di gruppo abbia aggiornato correttamente il Registro di sistema nel computer di un utente esaminando il Registro di sistema. Aprire l'editor del registro di sistema e passare alla chiave di ** \[\_Microsoft\\\\Office\] Lync del software\_\\\\utente corrente di HKEY** . Se l'oggetto Criteri di gruppo ha aggiornato correttamente il Registro di sistema, visualizzerai un valore denominato EnableSkypeUI con il valore 0.

</div>

</div>

<span> </span>

</div>

</div>

</div>

