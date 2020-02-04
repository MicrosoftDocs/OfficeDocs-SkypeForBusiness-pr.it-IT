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
ms.openlocfilehash: 2597bf31c9f0cc9f4316f505811426f2c9948a6f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41723852"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="request-and-configure-a-certificate-for-your-reverse-http-proxy-in-lync-server-2013"></a>Richiedere e configurare un certificato per il proxy inverso HTTP in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2014-02-14_

È necessario installare il certificato della CA (Root Certification Authority) nel server che ha eseguito Microsoft Forefront Threat Management Gateway 2010 o IIS ARR per l'infrastruttura CA che ha emesso i certificati del server nei server interni che hanno eseguito Microsoft Lync Server 2013.

È inoltre necessario installare un certificato del server Web pubblico nel server proxy inverso. I nomi alternativi dell'oggetto del certificato devono contenere i nomi di dominio completi esterni pubblicati di ogni pool che ospita gli utenti abilitati per l'accesso remoto e gli FQDN esterni di tutti i direttori o i pool di Director che verranno usati all'interno infrastruttura Edge. Il nome alternativo soggetto deve contenere anche l'URL semplice della riunione, l'URL semplice per la chiamata in accesso esterno e, se si distribuiscono le applicazioni mobili e si prevede di usare l'individuazione automatica, l'URL del servizio di rilevamento automatico esterni, come illustrato nella tabella seguente.


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
<td><p>Nome oggetto</p></td>
<td><p>FQDN del pool</p></td>
<td><p>webext.contoso.com</p></td>
</tr>
<tr class="even">
<td><p>Nome alternativo soggetto</p></td>
<td><p>FQDN del pool</p></td>
<td><p>webext.contoso.com</p>



> [!IMPORTANT]
> Il nome dell'oggetto deve essere presente anche nel nome dell'oggetto alternativo.

</td>
</tr>
<tr class="odd">
<td><p>Nome alternativo soggetto</p></td>
<td><p>Servizi Web di Director facoltativi (se Director è distribuito)</p></td>
<td><p>webdirext.contoso.com</p></td>
</tr>
<tr class="even">
<td><p>Nome alternativo soggetto</p></td>
<td><p>URL semplice della riunione</p>



> [!NOTE]
> Tutti gli URL semplici della riunione devono essere nel nome dell'oggetto alternativo. Ogni dominio SIP deve avere almeno un URL semplice della riunione attiva.

</td>
<td><p>meet.contoso.com</p></td>
</tr>
<tr class="odd">
<td><p>Nome alternativo soggetto</p></td>
<td><p>URL semplice con accesso esterno</p></td>
<td><p>dialin.contoso.com</p></td>
</tr>
<tr class="even">
<td><p>Nome alternativo soggetto</p></td>
<td><p>Server Office Web Apps</p></td>
<td><p>officewebapps01.contoso.com</p></td>
</tr>
<tr class="odd">
<td><p>Nome alternativo soggetto</p></td>
<td><p>URL del servizio di individuazione automatica esterna</p></td>
<td><p>lyncdiscover.contoso.com</p>



> [!NOTE]
> Se si usa anche Microsoft Exchange Server, sarà anche necessario configurare le regole per il proxy inverso per gli URL di Exchange Autodiscover e servizi Web.

</td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]
> Se la distribuzione interna è costituita da più server standard o pool Front-End, è necessario configurare le regole di pubblicazione Web per ogni FQDN della Web farm esterna e si avrà bisogno di un certificato e di un listener Web per ogni utente oppure è necessario ottenere un certificato il cui nome alternativo soggetto contiene i nomi usati da tutti i pool, assegnarlo a un listener Web e condividerlo tra più regole di pubblicazione Web.



</div>

<div>

## <a name="create-a-certificate-request"></a>Creare una richiesta di certificato

Si crea una richiesta di certificato nel proxy inverso. Si crea una richiesta in un altro computer, ma è necessario esportare il certificato firmato con la chiave privata e importarlo nel proxy inverso dopo averlo ricevuto dall'autorità di certificazione pubblica.

<div>


> [!NOTE]
> Una richiesta di certificato o una richiesta di firma del certificato (CSR) è una richiesta a un'autorità di certificazione pubblica (CA) attendibile per la convalida e la firma della chiave pubblica del computer richiedente. Quando viene generato un certificato, viene creata una chiave pubblica e una chiave privata. Solo la chiave pubblica è condivisa e firmata. Come suggerisce il nome, la chiave pubblica viene resa disponibile per qualsiasi richiesta pubblica. La chiave pubblica è destinata all'uso da parte di client, server e altri richiedenti che devono scambiare informazioni in modo sicuro e convalidare l'identità di un computer. La chiave privata viene mantenuta protetta e viene usata solo dal computer che ha creato la coppia di chiavi per decrittografare i messaggi crittografati con la relativa chiave pubblica. La chiave privata può essere usata per altri scopi. Per scopi di proxy inverso, la crittografia dei dati è l'uso principale. In secondo luogo, l'autenticazione del certificato a livello di chiave del certificato è un altro uso ed è limitata solo alla convalida che un richiedente ha la chiave pubblica del computer o che il computer in cui è presente una chiave pubblica è in realtà il computer che dichiara di essere.



</div>

<div>


> [!TIP]
> Se si pianificano contemporaneamente i certificati Edge Server e i certificati di proxy inverso, è necessario notare che esiste una notevole somiglianza tra i due requisiti di certificato. Quando si configura e richiede il certificato Edge Server, combinare il server perimetrale e i nomi alternativi dell'oggetto proxy inverso. È possibile usare lo stesso certificato per il proxy inverso se si esportano il certificato e la chiave privata e si copia il file esportato nel proxy inverso e quindi si importano le coppie di certificati e chiavi e le si assegnano le necessarie nelle procedure successive. Fare riferimento ai requisiti di certificato per il piano&nbsp;Edge Server<A href="lync-server-2013-plan-for-edge-server-certificates.md">per i certificati Edge Server in Lync Server 2013</A> e il riepilogo del proxy inverso per il <A href="lync-server-2013-certificate-summary-reverse-proxy.md">Reverse del certificato in Lync Server 2013</A>. Assicurarsi di creare il certificato con una chiave privata esportabile. La creazione della richiesta di certificato e certificato con una chiave privata esportabile è necessaria per i server perimetrali in pool, quindi si tratta di una pratica normale e la procedura guidata certificato nella distribuzione guidata di Lync Server per il server perimetrale consentirà di impostare il contrassegno di <STRONG>creazione della chiave privata esportabile</STRONG> . Dopo aver ricevuto la richiesta di certificato dall'autorità di certificazione pubblica, si esporterà il certificato e la chiave privata. Vedere la sezione "per esportare il certificato con la chiave privata per i server perimetrali in un pool" nell'argomento <A href="lync-server-2013-set-up-certificates-for-the-external-edge-interface.md">configurare i certificati per l'interfaccia esterna di Edge per Lync Server 2013</A> per informazioni dettagliate su come creare ed esportare il certificato con una chiave privata. L'estensione del certificato deve essere di tipo <STRONG>PFX</STRONG>.



</div>

Per generare una richiesta di firma del certificato nel computer in cui verrà assegnato il certificato e la chiave privata, eseguire le operazioni seguenti:

**Creazione di una richiesta di firma del certificato**

1.  Aprire Microsoft Management Console (MMC) e aggiungere lo snap-in certificati e selezionare **computer**, quindi espandere **personale**. Per informazioni dettagliate su come creare una console certificati in Microsoft Management Console (MMC), vedere [http://go.microsoft.com/fwlink/?LinkId=282616](http://go.microsoft.com/fwlink/?linkid=282616).

2.  Fare clic con il pulsante destro del mouse su **certificati**, scegliere **tutte le attività**, fare clic su **operazioni avanzate**e su **Crea richiesta personalizzata**.

3.  Nella pagina **registrazione certificati** fare clic su **Avanti**.

4.  Nella pagina **selezionare i criteri di registrazione dei certificati** in **richiesta personalizzata**Selezionare **continua senza criteri di registrazione**. Fare clic su **Avanti**.

5.  Nella pagina **richiesta personalizzata** , per il **modello** Selezionare **(nessun modello) chiave legacy**. Se non diversamente specificato dal provider di certificati, escludere le **estensioni predefinite** deselezionate e la selezione del **formato della richiesta** in **PKCS \#10**. Fare clic su **Avanti**.

6.  Nella pagina **informazioni certificato** fare clic su **Dettagli**e quindi su **proprietà**.

7.  Nella pagina **Proprietà certificato** della scheda **generale** del campo **nome descrittivo** digitare un nome per il certificato. Facoltativamente, digitare una descrizione nel campo **Descrizione** . Il nome descrittivo e la descrizione vengono in genere usati dall'amministratore per identificare la finalità del certificato, ad esempio il **listener del proxy inverso per Lync Server**.

8.  Selezionare la scheda **oggetto** . In **nome oggetto** per il **tipo**Selezionare **nome comune** per il tipo di nome soggetto. Per il **valore**, digitare il nome dell'oggetto che verrà usato per il proxy inverso e quindi fare clic su **Aggiungi**. Nell'esempio fornito nella tabella in questo argomento, il nome dell'oggetto è webext.contoso.com e verrebbe digitato nel campo valore per il nome dell'oggetto.

9.  Nella scheda **oggetto** in **nome alternativo**Selezionare **DNS** nell'elenco a discesa per **tipo**. Per ogni nome alternativo soggetto definito richiesto nel certificato, digitare il nome di dominio completo e quindi fare clic su **Aggiungi**. Ad esempio, nella tabella sono presenti tre nomi alternativi oggetto, meet.contoso.com, dialin.contoso.com e lyncdiscover.contoso.com. Nel campo **valore** Digitare meet.contoso.com, quindi fare clic su **Aggiungi**. Ripetere la procedura per ogni nome alternativo soggetto che è necessario definire.

10. Nella pagina **Proprietà certificato** fare clic sulla scheda **estensioni** . In questa pagina definirai gli scopi della chiave crittografica nell' **uso delle chiavi** e l'uso della chiave estesa nell'uso della chiave **estesa (criteri applicazione)**.

11. Fare clic sulla freccia **uso chiave** per visualizzare le **opzioni disponibili**. In opzioni disponibili fare clic su **firma digitale**, quindi fare clic su **Aggiungi**. Fare clic su **crittografia chiave**, quindi su **Aggiungi**. Se la casella di controllo per **rendere questi usi chiave Critical** è deselezionata, selezionare la casella di spunta.

12. Fare clic sulla freccia **uso esteso chiave (criteri applicazione)** per visualizzare le **opzioni disponibili**. In opzioni disponibili fare clic su **autenticazione server**e quindi su **Aggiungi**. Fare clic su **autenticazione client**, quindi fare clic su **Aggiungi**. Se la casella di controllo per **l'uso delle chiavi estese** è selezionata, deselezionare la casella. Contrariamente alla casella di controllo utilizzo chiave (che deve essere selezionata), è necessario assicurarsi che la casella di controllo utilizzo tasti esteso non sia selezionata.

13. Nella pagina **Proprietà certificato** fare clic sulla scheda **chiave privata** . fare clic sulla freccia **Opzioni chiave** . Per le **dimensioni della chiave**, selezionare **2048** nell'elenco a discesa. Se si sta generando questa coppia di chiavi e la RSI in un computer diverso dal proxy inverso per cui è destinato il certificato, selezionare **Rendi chiave privata esportabile**.
    
    <div>
    
    <table>
    <thead>
    <tr class="header">
    <th><img src="images/Gg398321.security(OCS.15).gif" title="sicurezza" alt="security" />Nota sulla sicurezza:</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td>La selezione di <strong>una chiave privata esportabile</strong> viene in genere consigliata quando si hanno più proxy inversa in una farm, perché il certificato e la chiave privata vengono copiati in ogni computer della farm. Se si consente la creazione di una chiave privata esportabile, è necessario prestare particolare attenzione al certificato e al computer in cui è stato generato. La chiave privata, se compromessa, renderà il certificato inutile e potenzialmente esporrà il computer o i computer all'accesso esterno e ad altre vulnerabilità della sicurezza.</td>
    </tr>
    </tbody>
    </table>
    
    </div>

14. Nella scheda **chiave privata** fare clic sulla freccia del **tipo di chiave** . Selezionare l'opzione di **Exchange** .

15. Fare clic su **OK** per salvare le **proprietà del certificato** impostate.

16. Nella pagina **registrazione certificati** fare clic su **Avanti**.

17. Nella pagina **dove si vuole salvare la richiesta offline?** , viene richiesto un **nome di file** e un **formato di file** per salvare la richiesta di firma del certificato.

18. Nel campo immissione **nome file** Digitare un percorso e un nome per la richiesta oppure fare clic su **Sfoglia** per selezionare una posizione per il file e digitare il nome file per la richiesta.

19. Per il **formato di file**, fare clic su **base 64** o **binario**. Selezionare **Base 64** a meno che non venga indicato diversamente dal fornitore per i certificati.

20. Individuare il file di richiesta salvato nel passaggio precedente. Invia alla tua autorità di certificazione pubblica.
    
    <div>
    

    > [!IMPORTANT]
    > Microsoft ha identificato le CA pubbliche che soddisfano i requisiti per scopi di comunicazioni unificate. Un elenco viene gestito nell'articolo della Knowledge Base seguente. <A href="http://go.microsoft.com/fwlink/?linkid=282625">http://go.microsoft.com/fwlink/?LinkId=282625</A>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

