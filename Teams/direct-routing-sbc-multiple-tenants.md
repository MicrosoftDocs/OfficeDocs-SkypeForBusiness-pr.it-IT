---
title: Configurare il controller dei confini della sessione - Più tenant
ms.reviewer: filippse
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: Informazioni su come configurare un controller dei confini di sessione (SBC) per servire più tenant per i partner Microsoft e/o i gestori PSTN.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 48a045ea84cabf34ec6f95b4aa0f605a3155d50e
ms.sourcegitcommit: f2253162a23d0683e7424211da1a0a8760c8a91b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/29/2022
ms.locfileid: "66240665"
---
# <a name="configure-a-session-border-controller-for-multiple-tenants"></a>Configurare un Session Border Controller per più tenant

Il routing diretto supporta la configurazione di un session border controller (SBC) per l'uso di più tenant.

> [!NOTE]
> Questo scenario è progettato per i partner e/o i gestori PSTN Microsoft, indicati come gestori più avanti in questo documento. Un vettore vende servizi di telefonia forniti a Microsoft Teams ai propri clienti. 

Un vettore:
- Distribuisce e gestisce una scheda SBC nel proprio data center (i clienti non devono implementare una scheda SBC e ricevono servizi di telefonia dal gestore nel client teams).
- Collega SBC a più tenant.
- Fornisce servizi PSTN (Public Switched Telephone Network) ai clienti.
- Gestisce la qualità delle chiamate end-to-end.
- Addebiti separati per i servizi PSTN.

Microsoft non gestisce i gestori telefonici. Microsoft offre Il sistema telefonico , un PBX (Private Branch Exchange) e un client teams. Microsoft certifica anche i telefoni e i certificati SBC che possono essere utilizzati con Sistema telefonico. Prima di scegliere un gestore telefonico, assicurati che la tua scelta disponga di un certificato SBC e possa gestire la qualità vocale end-to-end.

Di seguito sono riportati i passaggi di implementazione tecnica per configurare lo scenario.

**Solo vettore:**
1. Distribuire SBC e configurarlo per lo scenario di hosting in base alle [istruzioni dei fornitori certificati SBC](#deploy-and-configure-the-sbc).
2. Registrare un nome di dominio di base nel tenant del gestore telefonico e richiedere un certificato con caratteri jolly.
3. Registra un sottodominio per ogni cliente, che fa parte del dominio di base.

**Vettore con un amministratore globale del cliente:**
1. Aggiungere il nome del sottodominio al tenant del cliente.
2. Attivare il nome del sottodominio.
3. Configurare il trunk dal gestore al tenant del cliente ed eseguire il provisioning degli utenti.

*Assicurarsi di conoscere le nozioni di base sul DNS e come viene gestito il nome di dominio in Microsoft 365. Vedere [Ottenere assistenza per i domini di Microsoft 365](/microsoft-365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider) prima di procedere.*

## <a name="deploy-and-configure-the-sbc"></a>Distribuire e configurare SBC

Per la procedura dettagliata su come distribuire e configurare le schede SBC per uno scenario di hosting SBC, vedere la documentazione del fornitore di SBC.

- **Audiocodes:** Vedere [Le note sulla configurazione del routing diretto](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-Microsoft-Teams) per la configurazione dello scenario di hosting SBC, come descritto in "Connecting AudioCodes SBC to Microsoft Teams Direct Routing Hosting Model Configuration Note". 
- **Oracle:** Vedere [Note sulla configurazione del routing diretto](https://www.oracle.com/technetwork/indexes/documentation/acme-packet-2228107.html) per la configurazione dello scenario di hosting SBC, come descritto nella sezione "Microsoft". 
- **Comunicazioni sulla barra multifunzione:** Per la documentazione su come configurare le schede SBC della serie core della [barra multifunzione, vedere La guida alla configurazione di Microsoft Teams di base per le comunicazioni sulla barra multifunzione](https://support.sonus.net/display/IOT/PBXs+-+SBC+5k7kSWe) . Vedere anche [Procedure consigliate sulla barra multifunzione - Configurazione dei gestori per Microsoft Teams Direct Routing SBC Edge](https://support.sonus.net/display/UXDOC81/Connect+SBC+Edge+to+Microsoft+Teams+Direct+Routing+to+Support+Direct+Routing+Carrier)
- **TE-Systems (anynode):** Per la documentazione e gli esempi su come configurare anynode SBC per più tenant, eseguire la registrazione nel sito della [community di TE-Systems](https://community.te-systems.de/) .
- **Metaswitch:** Registrati nel sito della [pagina della community metaswitch](https://manuals.metaswitch.com/MAN39555) per la documentazione su come abilitare Perimeta SBC per più tenant.

> [!NOTE]
> Assicurarsi di sapere come configurare l'intestazione "Contatto". L'intestazione Contatto viene usata per trovare il tenant del cliente nel messaggio di invito in arrivo. 

## <a name="register-a-base-domain-and-subdomains"></a>Registrare un dominio di base e sottodomini

Per lo scenario di hosting, è necessario creare:

- Un nome di dominio di base di proprietà del gestore.
- Un sottodominio che fa parte del nome di dominio di base in ogni tenant del cliente.

Nell'esempio seguente:

- Adatum è un gestore che serve diversi clienti fornendo servizi internet e di telefonia.
- Woodgrove Bank, Contoso e Adventure Works sono tre clienti che hanno domini Microsoft 365 ma ricevono i servizi di telefonia da Adatum.

I sottodomini **DEVONO** corrispondere al nome FQDN del trunk che verrà configurato per il cliente e all'FQDN nell'intestazione Contatto quando si invia l'invito a Microsoft 365. 

Quando una chiamata arriva all'interfaccia Routing diretto di Microsoft 365, l'interfaccia usa l'intestazione Contatto per trovare il tenant in cui l'utente deve essere cercato. Il routing diretto non usa la ricerca del numero di telefono nell'opzione Invita, perché alcuni clienti potrebbero avere numeri non DID che possono sovrapporsi in diversi tenant. Di conseguenza, il nome FQDN nell'intestazione Contatto è necessario per identificare il tenant esatto in cui cercare l'utente in base al numero di telefono.

*Per altre informazioni sulla creazione di nomi di dominio nelle organizzazioni di Microsoft 365, vedere [Ottenere assistenza per i domini di Microsoft 365](/microsoft-365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider).*

Il diagramma seguente riepiloga i requisiti per il dominio di base, i sottodomini e l'intestazione contatto.

:::image type="content" source="media/direct-routing-1-sbc-requirements.png" alt-text="Diagramma che mostra i requisiti per i domini e l'intestazione contatto." lightbox="media/direct-routing-1-sbc-requirements.png":::

Il certificato SBC richiede un certificato per autenticare le connessioni. Per lo scenario di hosting SBC, il gestore deve richiedere un certificato con .base_domain CN e/o SAN (ad esempio, .customers.adatum.biz).For the SBC hosting scenario, the carrier needs to request a certificate with CN and/or SAN *\*.base_domain (ad esempio, \*.customers.adatum.biz)*. Questo certificato può essere usato per autenticare le connessioni a più tenant serviti da un singolo certificato SBC.

La tabella seguente è un esempio di configurazione.


|Nuovo nome di dominio |Tipo|Registrato  |Certificato CN/SAN per SBC  |Dominio predefinito tenant nell'esempio  |Nome FQDN che SBC deve presentare nell'intestazione Contatto quando si inviano chiamate agli utenti|
|---------|---------|---------|---------|---------|---------|
|customers.adatum.biz|    Base     |     Nel tenant del vettore  |    \*customers.adatum.biz  |   adatum.biz      |N/D, questo è un tenant di servizio, nessun utente |
|sbc1.customers.adatum.biz|    Sottodominio  |    In un tenant cliente  |    \*customers.adatum.biz  | woodgrovebank.us  |  sbc1.customers.adatum.biz|
|sbc2.customers.adatum.biz  |   Sottodominio | In un tenant cliente   |   \*customers.adatum.biz   |contoso.com   |sbc2.customers.adatum.biz |
|sbc3.customers.adatum.biz |   Sottodominio | In un tenant cliente |   \*customers.adatum.biz  |  adventureworks.com | sbc3.customers.adatum.biz |

Per configurare la base e i sottodomini, seguire la procedura descritta di seguito. Questo esempio configura un nome di dominio di base (customers.adatum.biz) e un sottodominio per un cliente (sbc1.customers.adatum.biz nel tenant di Woodgrove Bank).

> [!NOTE]
> Usare sbcX.customers.adatum.biz per abilitare la voce nel tenant del gestore telefonico; sbcX può essere qualsiasi nome host alfanumerico univoco e valido.

## <a name="register-a-base-domain-name-in-the-carrier-tenant"></a>Registrare un nome di dominio di base nel tenant del gestore telefonico

**Queste azioni vengono eseguite nel tenant del gestore telefonico.**

### <a name="ensure-that-you-have-appropriate-rights-in-the-carrier-tenant"></a>Assicurarsi di disporre dei diritti appropriati nel tenant del vettore

È possibile aggiungere nuovi domini solo se è stato eseguito l'accesso al interfaccia di amministrazione di Microsoft 365 come amministratore globale. 

Per convalidare il ruolo, accedere al interfaccia di amministrazione di Microsoft 365 (https://portal.office.com)passare a **Utenti attivi utenti** >  e quindi verificare di avere un ruolo di amministratore globale. 

Per altre informazioni sui ruoli di amministratore e su come assegnare un ruolo in Microsoft 365, vedere [Informazioni sui ruoli di amministratore](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d).

### <a name="add-a-base-domain-to-the-tenant-and-verify-it"></a>Aggiungere un dominio di base al tenant e verificarlo

1. Nel interfaccia di amministrazione di Microsoft 365 passare a **Setup** > **Domains** > **Add domain**.

2. Nella casella **Immettere un dominio di cui si è proprietari** digitare il nome di dominio completo del dominio di base. Nell'esempio seguente il dominio di base è *customers.adatum.biz*.

3. Fare clic su **Avanti**.

4. In questo esempio il tenant ha già adatum.biz come nome di dominio verificato. La procedura guidata non chiederà ulteriori verifiche perché customers.adatum.biz è un sottodominio per il nome già registrato. Tuttavia, se aggiungi un FQDN che non è stato verificato prima, dovrai completare il processo di verifica. Il processo di verifica è [descritto di seguito](#add-a-subdomain-to-the-customer-tenant-and-verify-it).

5. Selezionare **Avanti**, quindi nella pagina **Update DNS Settings** selezionare **I'll add the DNS records myself** e select **Next**.

6. Nella pagina successiva, cancellare tutti i valori (a meno che non si voglia usare il nome di dominio per Exchange, SharePoint, Teams o Skype for Business), selezionare **Avanti** e **quindi fine.** Verificare che lo stato del nuovo dominio sia Stato configurazione completata.

### <a name="activate-the-domain-name"></a>Attivare il nome di dominio

Dopo aver registrato un nome di dominio, è necessario attivarlo aggiungendo almeno un account utente o risorsa con licenza teams. Gli account accettabili verranno concessi in licenza con uno degli SKU seguenti:

- Account utente con Office 365 E1/E3/E5/A3/A5 o Microsoft 365 E3/E5/A3/A5
- Account utente con Office 365 F1/F3 o Microsoft 365 F1/F3
- Account utente con telefono area comune
- Account di risorsa con licenza utente virtuale

Inoltre, l'UPN dell'account (nome dell'entità utente) o Skype for Business'indirizzo SIP locale deve usare lo stesso FQDN del dominio appena creato.

Per altre informazioni sull'aggiunta di utenti nelle organizzazioni di Microsoft 365, vedere [Ottenere assistenza per i domini di Microsoft 365](/microsoft-365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider).

Ad esempio: test@customers.adatum.biz

![Screenshot della pagina di attivazione del dominio di base.](media/direct-routing-4-sbc-domain-activation.png)

## <a name="register-a-subdomain-name-in-a-customer-tenant"></a>Registrare un nome di sottodominio nel tenant di un cliente

Dovrai creare un nome di sottodominio univoco per ogni cliente. In questo esempio verrà creato un sottodominio sbc1.customers.adatum.biz in un tenant con il nome di dominio predefinito woodgrovebank.us.

**Tutte le azioni seguenti si trovano nel tenant del cliente.**

### <a name="ensure-that-you-have-appropriate-rights-in-the-customer-tenant"></a>Assicurarsi di disporre dei diritti appropriati nel tenant del cliente

È possibile aggiungere nuovi domini solo se è stato eseguito l'accesso al interfaccia di amministrazione di Microsoft 365 come amministratore globale. 

Per convalidare il ruolo, accedere al interfaccia di amministrazione di Microsoft 365 (https://portal.office.com)passare a **Utenti attivi utenti** >  e quindi verificare di avere un ruolo di amministratore globale. 

Per altre informazioni sui ruoli di amministratore e su come assegnare un ruolo in Microsoft 365, vedere [Informazioni sui ruoli di amministratore](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d).

### <a name="add-a-subdomain-to-the-customer-tenant-and-verify-it"></a>Aggiungere un sottodominio al tenant del cliente e verificarlo

1. Nel interfaccia di amministrazione di Microsoft 365 passare a **Setup** > **Domains** > **Add domain**.

2. Nella casella **Immettere un dominio di cui si è proprietari** digitare il nome di dominio completo del sottodominio per il tenant. Nell'esempio seguente il sottodominio è sbc1.customers.adatum.biz.

3. Selezionare **Avanti**.

4. L'FQDN non è mai stato registrato nel tenant. Nel passaggio successivo è necessario verificare il dominio. Selezionare **Aggiungi un record TXT**. 

5. Selezionare **Avanti** e prendere nota del valore TXT generato per verificare il nome di dominio.

    ![Screenshot dei record di testo nella pagina Verifica dominio.](media/direct-routing-7-sbc-verify-domain-txt.png)

6. Creare il record TXT con il valore del passaggio precedente nel provider di hosting DNS del gestore telefonico.

    Per altre informazioni, vedere [Creare record DNS presso qualsiasi provider di hosting DNS](https://support.office.com/article/create-dns-records-at-any-dns-hosting-provider-for-office-365-7b7b075d-79f9-4e37-8a9e-fb60c1d95166).

7. Vai alla interfaccia di amministrazione di Microsoft 365 del cliente e seleziona **Verifica**. 

8. Nella pagina successiva selezionare **Aggiungo personalmente i record DNS** e quindi **Avanti**.

9. Nella pagina **Scegli il Servizi online** deselezionare tutte le opzioni e selezionare **Avanti**.

10. Selezionare **Fine** nella pagina **Aggiorna impostazioni DNS** .

11. Verificare che lo stato sia **Installazione completata**. 
    
    ![Screenshot della pagina che mostra lo stato dell'installazione completata.](media/direct-routing-12-sbc-setup-complete.png)
    
> [!NOTE]
> L'URL di base e il sottodominio per il singolo client devono trovarsi nello stesso tenant per consentire l'aggiunta di un trunk _di route diretta_ .

### <a name="activate-the-subdomain-name"></a>Attivare il nome del sottodominio

Dopo aver registrato un nome di sottodominio, è necessario attivarlo aggiungendo almeno un account utente o risorsa con licenza di Teams. Gli account accettabili verranno concessi in licenza con uno degli SKU seguenti:
 
-   Account utente con Office 365 E1/E3/E5/A3/A5 o Microsoft 365 E3/E5/A3/A5
-   Account utente con Office 365 F1/F3 o Microsoft 365 F1/F3
-   Account utente con telefono area comune
-   Account di risorsa con licenza utente virtuale
 
Inoltre, l'UPN dell'account (nome dell'entità utente) o Skype for Business'indirizzo SIP locale deve usare lo stesso FQDN del sottodominio appena creato.

Per altre informazioni sull'aggiunta di utenti nelle organizzazioni di Microsoft 365, vedere [Ottenere assistenza per Microsoft 365](/microsoft-365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider).

Ad esempio: test@sbc1.customers.adatum.biz

![Screenshot della pagina Attivazione del sottodominio.](media/direct-routing-13-sbc-activate-subdomain.png)

### <a name="create-a-trunk-and-provision-users"></a>Creare un trunk e effettuare il provisioning degli utenti

Con la versione iniziale di Direct Routing, Microsoft richiedeva l'aggiunta di un trunk a ogni tenant servito (tenant del cliente) usando il cmdlet New-CSOnlinePSTNGateway.

Tuttavia, questo metodo non si è dimostrato ottimale per due motivi:
 
- **Gestione dell'overhead**. L'offload o lo svuotamento di un SBC, ad esempio, modifica alcuni parametri, come l'abilitazione o la disabilitazione del bypass multimediale. La modifica della porta richiede la modifica dei parametri in più tenant (eseguendo Set-CSOnlinePSTNGateway), ma in realtà è la stessa SBC. 

-  **Elaborazione overhead**. Raccolta e monitoraggio dei dati sanitari del trunk - Le opzioni SIP raccolte da più trunk logici che sono, in realtà, lo stesso SBC e lo stesso trunk fisico, rallentano l'elaborazione dei dati di routing.
 
In base a questo feedback, Microsoft sta introducendo una nuova logica per il provisioning dei trunk per i tenant dei clienti.

Sono state introdotte due nuove entità:

- Un trunk del corriere registrato nel tenant del corriere utilizzando il comando New-CSOnlinePSTNGateway. Ad esempio: 
   
   ```PowerShell
   New-CSOnlinePSTNGateway -FQDN customers.adatum.biz -SIPSignalingport 5068 -ForwardPAI $true
    ```

- Un trunk derivato che non richiede la registrazione. È semplicemente un nome host desiderato aggiunto dal trunk vettore. Deriva tutti i suoi parametri di configurazione dal trunk carrier. L'associazione con il trunk del gestore telefonico si basa sul nome FQDN (vedere i dettagli di seguito).

**Logica e esempio di provisioning**

- I gestori devono configurare e gestire solo un singolo trunk (il trunk del gestore nel dominio gestore) utilizzando il comando Set-CSOnlinePSTNGateway. Nell'esempio precedente è adatum.biz.

- Nel tenant del cliente, il gestore deve aggiungere il nome di dominio completo del trunk derivato alle route vocali. Non c'è bisogno di correre New-CSOnlinePSTNGateway per un baule.

- Il trunk derivato, come suggerisce il nome, eredita o ricava tutti i parametri di configurazione dal trunk carrier. 

Esempi:
- Customers.adatum.biz : il trunk del corriere che deve essere creato nel tenant del vettore.

- Sbc1.customers.adatum.biz: il trunk derivato in un tenant del cliente. È possibile aggiungere il nome del trunk derivato nel tenant del cliente nei criteri di routing vocale online senza crearlo.

- Il gestore telefonico dovrà configurare il record DNS che risolve l'FQDN del trunk derivato nell'indirizzo IP SBC del gestore.

- Le modifiche apportate a un trunk del corriere (nel tenant del vettore) vengono applicate automaticamente ai trunk derivati. Ad esempio, i gestori possono modificare una porta SIP nel trunk del gestore telefonico e questa modifica si applica a tutti i trunk derivati. La nuova logica per configurare i trunk semplifica la gestione in quanto non è necessario passare a ogni tenant e modificare il parametro in ogni trunk.

- Le opzioni vengono inviate solo all'FQDN del trunk del gestore telefonico. Lo stato di integrità del trunk del vettore viene applicato a tutti i trunk derivati e viene utilizzato per le decisioni di routing. Altre informazioni sulle [opzioni di Routing diretto](./direct-routing-monitor-and-troubleshoot.md).

- Il vettore può drenare il tronco portaerei, e tutti i tronchi derivati saranno drenati pure. 
 
> [!NOTE]
> Le regole di conversione dei numeri applicate al trunk del corriere non si applicano ai trunk derivati. Si tratta di un problema noto. Come soluzione alternativa, è necessario creare regole di traduzione dei numeri per il tenant di ogni cliente.

**Migrazione dal modello precedente al trunk del gestore telefonico**
 
Per la migrazione dall'implementazione corrente del modello ospitato dal gestore telefonico al nuovo modello, i gestori dovranno riconfigurare i trunk per i tenant dei clienti. Rimuovere i trunk dai tenant dei clienti usando Remove-CSOnlinePSTNGateway (lasciando il trunk nel tenant del vettore) -

È consigliabile eseguire la migrazione alla nuova soluzione il più presto possibile, in quanto miglioreremo il monitoraggio e il provisioning utilizzando la portaerei e il modello di trunk derivato.
 
Per altre informazioni sulla configurazione dell'invio del nome FQDN dei sottodomini nell'intestazione Contatto, vedere le [istruzioni del fornitore di SBC](#deploy-and-configure-the-sbc).

## <a name="considerations-for-setting-up-multi-tenant-failover"></a>Considerazioni sulla configurazione del failover multi-tenant 

Per configurare il failover per un ambiente multi-tenant, è necessario eseguire le operazioni seguenti:

- Per ogni tenant, aggiungere gli FQDN per due diversi SBC. Ad esempio:

   customer1.sbc1.contoso.com <br>
   customer1.sbc2.contoso.com <br>

- Nelle route vocali online specificare entrambi gli SBC. Se uno SBC non riesce, il criterio di routing instrada le chiamate al secondo SBC.


## <a name="see-also"></a>Vedere anche

[Pianificare Instradamento diretto](direct-routing-plan.md)

[Configurare Instradamento diretto](direct-routing-configure.md)
