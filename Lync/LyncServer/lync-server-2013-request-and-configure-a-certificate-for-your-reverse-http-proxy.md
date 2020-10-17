---
title: Richiedere e configurare un certificato per il proxy inverso HTTP
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Request and configure a certificate for your reverse HTTP proxy
ms:assetid: 4b70991e-5f10-40a3-b069-0b227c3a3a0a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429704(v=OCS.15)
ms:contentKeyID: 48184085
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7651e3da61e5ca197d36ca59ad8216af4c0188af
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48511983"
---
# <a name="request-and-configure-a-certificate-for-your-reverse-http-proxy-in-lync-server-2013"></a>Richiedere e configurare un certificato per il proxy inverso HTTP in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2014-02-14_

È necessario installare il certificato autorità di certificazione (CA) radice sul server che esegue Microsoft Forefront Threat Management Gateway 2010 o IIS ARR per l'infrastruttura CA che ha emesso i certificati server nei server interni che eseguono Microsoft Lync Server 2013.

È inoltre necessario installare un certificato server Web pubblico nel server proxy inverso. I nomi alternativi soggetto del certificato dovrebbero contenere i nomi di dominio completi (FQDN) esterni pubblicati di ogni pool che ospita gli utenti abilitati per l'accesso remoto e gli FQDN esterni di tutti i Director o pool di server Director che verranno utilizzati in tale infrastruttura Edge. Il nome alternativo soggetto deve contenere anche l'URL semplice della riunione, l'URL semplice di accesso esterno e, se si distribuiscono applicazioni mobili e si prevede di utilizzare l'individuazione automatica, l'URL del servizio di individuazione automatica esterno come illustrato nella tabella seguente.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th>Valore</th>
<th>Esempio</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Nome soggetto</p></td>
<td><p>FQDN del pool</p></td>
<td><p>webext.contoso.com</p></td>
</tr>
<tr class="even">
<td><p>Nome alternativo soggetto</p></td>
<td><p>FQDN del pool</p></td>
<td><p>webext.contoso.com</p>



> [!IMPORTANT]
> Il nome soggetto deve essere presente anche nel nome alternativo soggetto.

</td>
</tr>
<tr class="odd">
<td><p>Nome alternativo soggetto</p></td>
<td><p>Servizi Web Director opzionali (se il Director è distribuito)</p></td>
<td><p>webdirext.contoso.com</p></td>
</tr>
<tr class="even">
<td><p>Nome alternativo soggetto</p></td>
<td><p>URL semplice riunione</p>



> [!NOTE]
> Tutti gli URL semplici di riunione devono essere inclusi nel nome alternativo soggetto. Ogni dominio SIP deve avere almeno un URL semplice di riunione attiva.

</td>
<td><p>meet.contoso.com</p></td>
</tr>
<tr class="odd">
<td><p>Nome alternativo soggetto</p></td>
<td><p>URL semplice accesso esterno</p></td>
<td><p>dialin.contoso.com</p></td>
</tr>
<tr class="even">
<td><p>Nome alternativo soggetto</p></td>
<td><p>server Office Web Apps</p></td>
<td><p>officewebapps01.contoso.com</p></td>
</tr>
<tr class="odd">
<td><p>Nome alternativo soggetto</p></td>
<td><p>URL servizio di individuazione automatica esterno</p></td>
<td><p>lyncdiscover.contoso.com</p>



> [!NOTE]
> Se si utilizza anche Microsoft Exchange Server, sarà inoltre necessario configurare le regole del proxy inverso per gli URL di individuazione automatica e servizi Web di Exchange.

</td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]
> Se la distribuzione interna include più server Standard Edition o pool Front End, è necessario configurare le regole di pubblicazione Web per ogni FQDN di Web FARM esterna e sarà necessario un certificato e un listener Web per ognuno oppure ottenere un certificato con nome alternativo soggetto che contiene i nomi utilizzati da tutti i pool, assegnarlo a un listener Web e condividerlo tra più regole di pubblicazione Web.



</div>

<div>

## <a name="create-a-certificate-request"></a>Creare una richiesta di certificato

È possibile creare una richiesta di certificato per il proxy inverso. È possibile creare una richiesta su un altro computer, ma è necessario esportare il certificato firmato con la chiave privata e importarlo nel proxy inverso dopo averlo ricevuto dall'autorità di certificazione pubblica.

<div>


> [!NOTE]
> Una richiesta di certificato o una richiesta di firma del certificato (CSR) è una richiesta a un'autorità di certificazione (CA) pubblica attendibile per convalidare e firmare la chiave pubblica del computer richiedente. Quando viene generato un certificato, vengono create una chiave pubblica e una chiave privata. Solo la chiave pubblica è condivisa e firmata. Come suggerisce il nome, la chiave pubblica viene messa a disposizione di qualsiasi richiesta pubblica. La chiave pubblica è destinata all'utilizzo da parte di client, server e altri richiedenti che devono scambiare informazioni in modo sicuro e convalidare l'identità di un computer. La chiave privata viene mantenuta protetta e viene utilizzata solo dal computer che ha creato la coppia di chiavi per decrittografare i messaggi crittografati con la chiave pubblica. La chiave privata può essere utilizzata per altri scopi. Per motivi di proxy inverso, la crittografia dei dati è l'utilizzo principale. In secondo luogo, l'autenticazione del certificato a livello di chiave del certificato è un altro utilizzo ed è limitata solo alla convalida che un richiedente ha la chiave pubblica del computer o che il computer in cui si dispone di una chiave pubblica è effettivamente il computer che afferma di essere.



</div>

<div>


> [!TIP]
> Se si pianificano contemporaneamente i certificati del server perimetrale e i certificati per il proxy inverso, è necessario tenere presente che esiste una notevole somiglianza tra i due requisiti del certificato. Quando si configura e si richiede il certificato del server perimetrale, combinare il server perimetrale e i nomi alternativi del soggetto del proxy inverso. È possibile utilizzare lo stesso certificato per il proxy inverso se si esporta il certificato e la chiave privata e si copia il file esportato nel proxy inverso e quindi si importa la coppia di certificati/chiavi e la si assegna come necessario nelle procedure imminenti. Fare riferimento ai requisiti del certificato per il piano server perimetrale &nbsp; <A href="lync-server-2013-plan-for-edge-server-certificates.md">per i certificati server perimetrali in lync Server 2013</A> e il riepilogo dei certificati del proxy inverso <A href="lync-server-2013-certificate-summary-reverse-proxy.md">-proxy inverso in Lync Server 2013</A>. Assicurarsi di creare il certificato con una chiave privata esportabile. Per creare il certificato e la richiesta di certificato con una chiave privata esportabile, è necessario eseguire una procedura normale e la configurazione guidata certificati nella distribuzione guidata di Lync Server per il server perimetrale consentirà di impostare il flag <STRONG>Rendi la chiave privata esportabile</STRONG> . Dopo aver ricevuto la richiesta di certificato dall'autorità di certificazione pubblica, verranno esportati il certificato e la chiave privata. Vedere la sezione "per esportare il certificato con la chiave privata per i server perimetrali in un pool" nell'argomento <A href="lync-server-2013-set-up-certificates-for-the-external-edge-interface.md">configurare i certificati per l'interfaccia perimetrale esterna per Lync Server 2013</A> per informazioni dettagliate su come creare ed esportare il certificato con una chiave privata. L'estensione del certificato deve essere di tipo <STRONG>PFX</STRONG>.



</div>

Per generare una richiesta di firma del certificato nel computer in cui verrà assegnato il certificato e la chiave privata, eseguire le operazioni seguenti:

**Creazione di una richiesta di firma del certificato**

1.  Aprire Microsoft Management Console (MMC) e aggiungere lo snap-in certificati e selezionare **computer**, quindi espandere **personale**. Per informazioni dettagliate su come creare una console di certificati in Microsoft Management Console (MMC), vedere [https://go.microsoft.com/fwlink/?LinkId=282616](https://go.microsoft.com/fwlink/?linkid=282616) .

2.  Fare clic con il pulsante destro del mouse su **certificati**, scegliere **tutte le attività**, fare clic su **operazioni avanzate**, su **Crea richiesta personalizzata**.

3.  Nella pagina **registrazione certificati** fare clic su **Avanti**.

4.  Nella pagina **selezionare il criterio di registrazione dei certificati** in **richiesta personalizzata**, selezionare **continua senza criteri di registrazione**. Fare clic su **Avanti**.

5.  Nella pagina **richiesta personalizzata** , per la **Template** **chiave legacy template Select (No Template)**. Se non diversamente specificato dal provider di certificati, lasciare invariate le **estensioni predefinite** deselezionate e la selezione del **formato di richiesta** su **PKCS \# 10**. Fare clic su **Avanti**.

6.  Nella pagina **informazioni sui certificati** fare clic su **Dettagli**e quindi su **proprietà**.

7.  Nella pagina delle **proprietà del certificato** nella scheda **generale** del campo **nome descrittivo** digitare un nome per il certificato. Facoltativamente, digitare una descrizione nel campo **Descrizione** . Il nome descrittivo e la descrizione vengono in genere utilizzati dall'amministratore per identificare lo scopo del certificato, ad esempio il **listener del proxy inverso per Lync Server**.

8.  Selezionare la scheda **oggetto** . In **nome oggetto** per il **tipo**Selezionare **nome comune** per il tipo di nome soggetto. Per il **valore**, digitare il nome del soggetto che verrà utilizzato per il proxy inverso, quindi fare clic su **Aggiungi**. Nell'esempio fornito nella tabella di questo argomento, il nome del soggetto è webext.contoso.com e verrebbe digitato nel campo valore per il nome del soggetto.

9.  Nella scheda **oggetto** in **nome alternativo**Selezionare **DNS** dal menu a discesa per **tipo**. Per ogni nome alternativo del soggetto definito necessario per il certificato, digitare il nome di dominio completo e quindi fare clic su **Aggiungi**. Ad esempio, nella tabella sono presenti tre nomi alternativi del soggetto, meet.contoso.com, dialin.contoso.com e lyncdiscover.contoso.com. Nel campo **valore** Digitare meet.contoso.com, quindi fare clic su **Aggiungi**. Ripetere l'argomento per ogni nome alternativo del soggetto che è necessario definire.

10. Nella pagina delle **proprietà del certificato** fare clic sulla scheda **estensioni** . In questa pagina vengono definiti i fini della chiave di crittografia **nell'utilizzo delle chiavi e l'** utilizzo delle chiavi estese nell'utilizzo delle **chiavi estese (criteri applicazione)**.

11. Fare clic sulla freccia **utilizzo chiave** per visualizzare le **opzioni disponibili**. In opzioni disponibili fare clic su **firma digitale**e quindi su **Aggiungi**. Fare clic su **crittografia chiave**, quindi fare clic su **Aggiungi**. Se la casella di controllo per **rendere questi utilizzi fondamentali** è deselezionata, selezionare la casella di spunta.

12. Fare clic sulla freccia **utilizzo chiave estesa (criteri applicazione)** per visualizzare le **opzioni disponibili**. In opzioni disponibili fare clic su **autenticazione server**e quindi su **Aggiungi**. Fare clic su **autenticazione client**e quindi su **Aggiungi**. Se viene selezionata la casella di controllo **Rendi la chiave estesa utilizzazioni critiche** , deselezionare la casella di spunta. In caso contrario alla casella di controllo utilizzo chiave (che deve essere controllata), è necessario verificare che la casella di controllo utilizzo chiavi estese non sia selezionata.

13. Nella pagina delle **proprietà del certificato** , fare clic sulla scheda **chiave privata** . Fare clic sulla freccia **Opzioni chiave** . Per le **dimensioni della chiave**, selezionare **2048** dal menu a discesa. Se si sta generando questa coppia di chiavi e la RSI su un computer diverso da quello inverso per cui è destinato il certificato, selezionare **Rendi esportazione chiave privata**.
    
    <div>
    
    <table>
    <thead>
    <tr class="header">
    <th><img src="images/Gg398321.security(OCS.15).gif" title="sicurezza" alt="security" />Nota sulla sicurezza:</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td>La selezione di <strong>una chiave privata esportabile</strong> viene generalmente consigliata quando si dispone di più di un proxy inverso in una farm, in quanto il certificato e la chiave privata vengono copiati in ogni computer della farm. Se si consente la possibilità di utilizzare una chiave privata esportabile, è necessario prestare particolare attenzione al certificato e al computer in cui è stato generato. La chiave privata, se compromessa, renderà il certificato inutilizzabile e potrebbe esporre il computer o i computer all'accesso esterno e ad altre vulnerabilità della sicurezza.</td>
    </tr>
    </tbody>
    </table>
    
    </div>

14. Nella scheda **chiave privata** fare clic sulla freccia del **tipo di chiave** . Selezionare l'opzione di **Exchange** .

15. Fare clic su **OK** per salvare le **proprietà del certificato** impostate.

16. Nella pagina **registrazione certificati** fare clic su **Avanti**.

17. Nel percorso in **cui si desidera salvare la richiesta offline** , viene richiesto un **nome di file** e un formato di **file** per il salvataggio della richiesta di firma del certificato.

18. Nel campo immissione **nome file** Digitare un percorso e un nome file per la richiesta oppure fare clic su **Sfoglia** per selezionare un percorso per il file e digitare il nome della richiesta.

19. Per il **formato di file**, fare clic su **base 64** o **binario**. Selezionare **Base 64** a meno che non venga indicato altrimenti dal fornitore per i certificati.

20. Individuare il file di richiesta salvato nel passaggio precedente. Invia all'autorità di certificazione pubblica.
    
    <div>
    

    > [!IMPORTANT]
    > Microsoft ha identificato le CA pubbliche che soddisfano i requisiti per le comunicazioni unificate. Un elenco viene mantenuto nell'articolo della Knowledge Base seguente. <A href="https://go.microsoft.com/fwlink/?linkid=282625">https://go.microsoft.com/fwlink/?LinkId=282625</A>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

