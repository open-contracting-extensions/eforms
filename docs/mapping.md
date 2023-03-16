# Field mappings

## How to read the mappings table

<div class="wy-table-responsive">
  <table class="docutils">
    <colgroup>
      <col width="30%">
      <col width="70%">
    </colgroup>
    <tbody>
      <tr>
        <td>
            <p><b>The field's ID</b> <a class="reference external" href="#" title="A link to the field's description in the eForms SDK"></a><br>The field's title</p><p><i>The ID of the business term to which the field is associated:</i> The business term's description.</p>
            <code class="docutils literal notranslate"><span class="pre">The XPath that uniquely corresponds to this field.</span></code>
        </td>
        <td>

Instructions to follow to map the eForms field to OCDS.

```xml
<snippet of="XML">
  This snippet is typically taken directly from the eForms SDK's documentation.
</snippet>
```

```json
{
  "An abbreviated OCDS release": "that corresponds to the XML snippet above."
}
```

</td>
    </tr>
  </tbody>
</table>

## Mappings table

<!-- Do not edit past this point. It is managed by european-union-support. -->

<div id="mappings" class="wy-table-responsive">
  <p>
    <label for="mappings-search">
      Search the table by eForms field, business term, XML element, OCDS field, etc.:
    </label>
    <input id="mappings-search" class="search" placeholder="Search">
  </p>
  <table class="docutils">
    <colgroup>
      <col width="30%">
      <col width="70%">
    </colgroup>
    <thead>
      <tr>
        <th>eForms field</th>
        <th>OCDS mapping</th>
      </tr>
    </thead>
    <tbody class="list">
      <tr id="BT-01(c)-Procedure">
        <td class="field break-all">
            <p><b>BT-01(c)-Procedure</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/procedure-lot-part-information.html#otherLegalBasisSection"></a><br>Procedure Legal Basis (ID)</p><p><i>BT-01:</i> The legal basis (e.g. a Union or national legal act) under which the procurement procedure takes place or, in case of prior information notices, under which the procurement procedure(s) will take place.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:TenderingTerms/cac:ProcurementLegislationDocumentReference[not(cbc:ID/text()=('CrossBorderLaw','LocalLegalBasis'))]/cbc:ID[not(text()=('CrossBorderLaw','LocalLegalBasis'))]</span></code>
        </td>
        <td class="mapping">

Set `tender.legalBasis.scheme` to <a href="https://eur-lex.europa.eu/eli-register/about.html">'ELI'</a>, and map to `tender.legalBasis.id`.

```xml
<cac:ProcurementLegislationDocumentReference>
  <cbc:ID schemeName="ELI">http://data.europa.eu/eli/dir/2014/24/oj</cbc:ID>
</cac:ProcurementLegislationDocumentReference>
```

```json
{
  "tender": {
    "legalBasis": {
      "scheme": "ELI",
      "id": "http://data.europa.eu/eli/dir/2014/24/oj"
    }
  }
}
```

</td>
      </tr>
      <tr id="BT-01(d)-Procedure">
        <td class="field break-all">
            <p><b>BT-01(d)-Procedure</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/procedure-lot-part-information.html#otherLegalBasisSection"></a><br>Procedure Legal Basis (Description)</p><p><i>BT-01:</i> The legal basis (e.g. a Union or national legal act) under which the procurement procedure takes place or, in case of prior information notices, under which the procurement procedure(s) will take place.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:TenderingTerms/cac:ProcurementLegislationDocumentReference[not(cbc:ID/text()=('CrossBorderLaw','LocalLegalBasis'))]/cbc:DocumentDescription</span></code>
        </td>
        <td class="mapping">

Map to `tender.legalBasis.description`.

```xml
<cac:ProcurementLegislationDocumentReference>
  <cbc:DocumentDescription languageID="ENG">Directive XYZ applies ...</cbc:DocumentDescription>
</cac:ProcurementLegislationDocumentReference>
```

```json
{
  "tender": {
    "legalBasis": {
      "description": "Directive XYZ applies ..."
    }
  }
}
```

</td>
      </tr>
      <tr id="BT-01(e)-Procedure">
        <td class="field break-all">
            <p><b>BT-01(e)-Procedure</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/procedure-lot-part-information.html#otherLegalBasisSection"></a><br>Procedure Legal Basis (NoID)</p><p><i>BT-01:</i> The legal basis (e.g. a Union or national legal act) under which the procurement procedure takes place or, in case of prior information notices, under which the procurement procedure(s) will take place.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:TenderingTerms/cac:ProcurementLegislationDocumentReference[cbc:ID/text()='LocalLegalBasis']/cbc:ID[text()='LocalLegalBasis']</span></code>
        </td>
        <td class="mapping">

Map to `tender.legalBasis.id`.

```xml
<cac:ProcurementLegislationDocumentReference>
  <cbc:ID>LocalLegalBasis</cbc:ID>
</cac:ProcurementLegislationDocumentReference>
```

```json
{
  "tender": {
    "legalBasis": {
      "id": "LocalLegalBasis"
    }
  }
}
```

</td>
      </tr>
      <tr id="BT-01(f)-Procedure">
        <td class="field break-all">
            <p><b>BT-01(f)-Procedure</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/procedure-lot-part-information.html#otherLegalBasisSection"></a><br>Procedure Legal Basis (NoID Description)</p><p><i>BT-01:</i> The legal basis (e.g. a Union or national legal act) under which the procurement procedure takes place or, in case of prior information notices, under which the procurement procedure(s) will take place.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:TenderingTerms/cac:ProcurementLegislationDocumentReference[cbc:ID/text()='LocalLegalBasis']/cbc:DocumentDescription</span></code>
        </td>
        <td class="mapping">

Map to `tender.legalBasis.description`.

```xml
<cac:ProcurementLegislationDocumentReference>
  <cbc:DocumentDescription languageID="ENG">Directive XYZ applies ...</cbc:DocumentDescription>
</cac:ProcurementLegislationDocumentReference>
```

```json
{
  "tender": {
    "legalBasis": {
      "description": "Directive XYZ applies ..."
    }
  }
}
```

</td>
      </tr>
      <tr id="BT-01-notice">
        <td class="field break-all">
            <p><b>BT-01-notice</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/notice-information.html#legalBasisSection"></a><br>Procedure Legal Basis</p><p><i>BT-01:</i> The legal basis (e.g. a Union or national legal act) under which the procurement procedure takes place or, in case of prior information notices, under which the procurement procedure(s) will take place.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cbc:RegulatoryDomain</span></code>
        </td>
        <td class="mapping">

Set `tender.legalBasis.scheme` to <a href="https://eur-lex.europa.eu/content/help/faq/intro.html#help8">'CELEX'</a>, and map to `tender.legalBasis.id`.

```xml
<cbc:RegulatoryDomain>32014L0024</cbc:RegulatoryDomain>
```

```json
{
  "tender": {
    "legalBasis": {
      "scheme": "CELEX",
      "id": "32014L0024"
    }
  }
}
```

</td>
      </tr>
      <tr id="BT-02-notice">
        <td class="field break-all">
            <p><b>BT-02-notice</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/notice-information.html#subtypeSection"></a><br>Notice Type</p><p><i>BT-02:</i> The type of notice according to procurement legislation.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cbc:NoticeTypeCode</span></code>
        </td>
        <td class="mapping">

Discard.

```xml
<cbc:NoticeTypeCode>veat</cbc:NoticeTypeCode>
```



</td>
      </tr>
      <tr id="BT-03-notice">
        <td class="field break-all">
            <p><b>BT-03-notice</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/notice-information.html#subtypeSection"></a><br>Form Type</p><p><i>BT-03:</i> The type of form according to procurement legislation.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cbc:NoticeTypeCode/@listName</span></code>
        </td>
        <td class="mapping">

The codes are drawn from the <a href="https://op.europa.eu/en/web/eu-vocabularies/concept-scheme/-/resource?uri=http://publications.europa.eu/resource/authority/form-type">Form type</a> authority table in EU Vocabularies.

Look-up the code in the <a href="codelists/form-type">form type mapping table</a>, add the values of the release tag column to `tag` and set `tender.status` to the value of the tender status column.

```xml
<cbc:NoticeTypeCode listName="competition">cn-standard</cbc:NoticeTypeCode>
```

```json
{
  "tag": [
    "tender"
  ],
  "tender": {
    "status": "active"
  }
}
```

</td>
      </tr>
      <tr id="BT-04-notice">
        <td class="field break-all">
            <p><b>BT-04-notice</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/notice-information.html#procedureIDSection"></a><br>Procedure Identifier</p><p><i>BT-04:</i> The European Public Procurement Procedure Identifier, a unique identifier of a procurement procedure. Including this identifier in all published versions of this notice (e.g. published on TED, national publication portals, regional publication portals) allows unique identification of procurement procedures around the Union.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cbc:ContractFolderID</span></code>
        </td>
        <td class="mapping">

Map to `tender.id`.

```xml
<cbc:ContractFolderID>1e86a664-ae3c-41eb-8529-0242ac130003</cbc:ContractFolderID>
```

```json
{
  "tender": {
    "id": "1e86a664-ae3c-41eb-8529-0242ac130003"
  }
}
```

</td>
      </tr>
      <tr id="BT-05(a)-notice">
        <td class="field break-all">
            <p><b>BT-05(a)-notice</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/notice-information.html#dispatchDateSection"></a><br>Notice Dispatch Date</p><p><i>BT-05:</i> The date and time when the notice has been sent for publication by the buyer.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cbc:IssueDate</span></code>
        </td>
        <td class="mapping">

Combine with <a href="#BT-05(b)-notice">BT-05(b)-notice</a>, <a href="operations.md#convert-a-date-to-iso-format">convert date to ISO format</a> and map to `date`.

```xml
<cbc:IssueDate>2019-11-26+01:00</cbc:IssueDate>
<cbc:IssueTime>13:38:54+01:00</cbc:IssueTime>
```

```json
{
  "date": "2019-11-26T13:38:54+01:00"
}
```

</td>
      </tr>
      <tr id="BT-05(b)-notice">
        <td class="field break-all">
            <p><b>BT-05(b)-notice</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/notice-information.html#dispatchDateSection"></a><br>Notice Dispatch Time</p><p><i>BT-05:</i> The date and time when the notice has been sent for publication by the buyer.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cbc:IssueTime</span></code>
        </td>
        <td class="mapping">

Combine with <a href="#BT-05(a)-notice">BT-05(a)-notice</a>, <a href="operations.md#convert-a-date-to-iso-format">convert date to ISO format</a> and map to `date`.

```xml
<cbc:IssueDate>2019-11-26+01:00</cbc:IssueDate>
<cbc:IssueTime>13:38:54+01:00</cbc:IssueTime>
```

```json
{
  "date": "2019-11-26T13:38:54+01:00"
}
```

</td>
      </tr>
      <tr id="BT-06-Lot">
        <td class="field break-all">
            <p><b>BT-06-Lot</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/procedure-lot-part-information.html#strategicProcurementSection"></a><br>Strategic Procurement</p><p><i>BT-06:</i> The procurement procedure aims at reducing the environmental impacts of the procurement, fulfilling social objectives and/or buying an innovative work, supply or service.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='Lot']/cac:ProcurementProject/cac:ProcurementAdditionalType[cbc:ProcurementTypeCode/@listName='strategic-procurement']/cbc:ProcurementTypeCode[@listName='strategic-procurement']</span></code>
        </td>
        <td class="mapping">

This field maps to the same `Sustainability` objects as created for BT-777-Lot.

<a href="operations.md#get-the-lot-for-a-procurementprojectlot">Get the lot for the ProcurementProjectLot</a>.

If the code is "none" discard, otherwise set the lot's `.hasSustainability` to "true".

For each `cac:ProcurementAdditionalType`, add or update the corresponding `Sustainability` object to the lot's `.sustainability` array.

- Map the code to the sustainability's `.goal` according to the <a href="codelists/strategic-procurement">strategic procurement mapping table</a>.
- Add 'awardCriteria', 'contractPerformanceConditions', 'selectionCriteria' and 'technicalSpecifications' to the sustainability's `.strategies` array.

```xml
<cac:ProcurementAdditionalType>
  <cbc:ProcurementTypeCode listName="strategic-procurement">inn-pur</cbc:ProcurementTypeCode>
</cac:ProcurementAdditionalType>
```

```json
{
  "tender": {
    "lots": [
      {
        "hasSustainability": true,
        "sustainability": [
          {
            "goal": "economic.innovativePurchase",
            "strategies": [
              "awardCriteria",
              "contractPerformanceConditions",
              "selectionCriteria",
              "technicalSpecifications"
            ]
          }
        ]
      }
    ]
  }
}
```

</td>
      </tr>
      <tr id="BT-09(a)-Procedure">
        <td class="field break-all">
            <p><b>BT-09(a)-Procedure</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/procedure-lot-part-information.html#crossBorderLawSection"></a><br>Cross Border Law</p><p><i>BT-09:</i> The applicable law when buyers from different countries procure together within one procurement procedure.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:TenderingTerms/cac:ProcurementLegislationDocumentReference[cbc:ID/text()='CrossBorderLaw']/cbc:ID[text()='CrossBorderLaw']</span></code>
        </td>
        <td class="mapping">

See <a href="#BT-09(b)-Procedure">BT-09(b)-Procedure</a>.





</td>
      </tr>
      <tr id="BT-09(b)-Procedure">
        <td class="field break-all">
            <p><b>BT-09(b)-Procedure</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/procedure-lot-part-information.html#crossBorderLawSection"></a><br>Cross Border Law Description</p><p><i>BT-09:</i> The applicable law when buyers from different countries procure together within one procurement procedure.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:TenderingTerms/cac:ProcurementLegislationDocumentReference[cbc:ID/text()='CrossBorderLaw']/cbc:DocumentDescription</span></code>
        </td>
        <td class="mapping">

Map to `tender.crossBorderLaw`.

```xml
<cac:ProcurementLegislationDocumentReference>
  <cbc:ID>CrossBorderLaw</cbc:ID>
  <cbc:DocumentDescription languageID="ENG">Directive XYZ on Cross Border ...</cbc:DocumentDescription>
</cac:ProcurementLegislationDocumentReference>
```

```json
{
  "tender": {
    "crossBorderLaw": "Directive XYZ on Cross Border ..."
  }
}
```

</td>
      </tr>
      <tr id="BT-10-Procedure-Buyer">
        <td class="field break-all">
            <p><b>BT-10-Procedure-Buyer</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/parties.html#_buyer_information"></a><br>Activity Authority</p><p><i>BT-10:</i> The main activity of the contracting authority.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ContractingParty/cac:ContractingActivity/cbc:ActivityTypeCode[@listName='authority-activity']</span></code>
        </td>
        <td class="mapping">

- <a href="operations.md#get-the-organization-for-the-buyer">Get the organization for the buyer</a> and add a `Classification` object to its `.details.classifications` array.
- Map the value of this field to the classification's `.id`.
- Look up the code's label in the <a href="https://op.europa.eu/en/web/eu-vocabularies/concept-scheme/-/resource?uri=http://publications.europa.eu/resource/authority/main-activity">authority table</a> and map it to the classification's `.description`.
- If the code's definition in the authority table includes <a href="https://ec.europa.eu/eurostat/statistics-explained/index.php?title=Glossary:Classification_of_the_functions_of_government_(COFOG)">"COFOG"</a>, set the classification's `.scheme` to 'COFOG'. Otherwise, set it to 'Directive 2014/25/EU'.

```xml
<cac:ContractingParty>
  <cac:Party>
    <cac:PartyIdentification>
      <cbc:ID schemeName="organization">ORG-0001</cbc:ID>
    </cac:PartyIdentification>
  </cac:Party>
  <cac:ContractingActivity>
    <cbc:ActivityTypeCode listName="authority-activity">gas-oil</cbc:ActivityTypeCode>
  </cac:ContractingActivity>
</cac:ContractingParty>
```

```json
{
  "parties": [
    {
      "id": "ORG-0001",
      "details": {
        "classifications": [
          {
            "scheme": "Directive 2014/25/EU",
            "id": "gas-oil",
            "description": "Activities related to the exploitation of a geographical area for the purpose of extracting oil or gas."
          }
        ]
      }
    }
  ]
}
```

</td>
      </tr>
      <tr id="BT-105-Procedure">
        <td class="field break-all">
            <p><b>BT-105-Procedure</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/procedure-lot-part-information.html#procedureTypeSection"></a><br>Procedure Type</p><p><i>BT-105:</i> The type of procurement procedure (e.g. according to the types given in the Public Procurement Directives mentioned in the recitals of this Act).</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:TenderingProcess/cbc:ProcedureCode</span></code>
        </td>
        <td class="mapping">

The codes are drawn from the <a href="https://op.europa.eu/en/web/eu-vocabularies/concept-scheme/-/resource?uri=http://publications.europa.eu/resource/authority/procurement-procedure-type">procurement procedure type</a>) authority table in EU Vocabularies.

Map to `tender.procurementMethod` according to the <a href="codelists/procurement-procedure-type">procurement procedure type mapping table</a>.

```{note}
`tender.procurementMethod` is not set for "oth-mult" or "oth-single".
```

```xml
<cbc:ProcedureCode listName="procurement-procedure-type">open</cbc:ProcedureCode>
```

```json
{
  "tender": {
    "procurementMethod": "open",
    "procurementMethodDetails": "Open procedure"
  }
}
```

</td>
      </tr>
      <tr id="BT-106-Procedure">
        <td class="field break-all">
            <p><b>BT-106-Procedure</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/procedure-lot-part-information.html#acceleratedProcedureSection"></a><br>Procedure Accelerated</p><p><i>BT-106:</i> The time limit for receipt of requests to participate or of tenders in this procedure can be reduced due to a state of urgency.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:TenderingProcess/cac:ProcessJustification[cbc:ProcessReasonCode/@listName='accelerated-procedure']/cbc:ProcessReasonCode[@listName='accelerated-procedure']</span></code>
        </td>
        <td class="mapping">

Map to `tender.procedure.isAccelerated` as a boolean.

```{seealso}
<a href="#BT-1351-Procedure">BT-1351-Procedure</a>
```

```xml
<cac:ProcessJustification>
  <cbc:ProcessReasonCode listName="accelerated-procedure">true</cbc:ProcessReasonCode>
  <cbc:ProcessReason languageID="ENG">Direct award is justified ...</cbc:ProcessReason>
</cac:ProcessJustification>
```

```json
{
  "tender": {
    "procedure": {
      "isAccelerated": true
    }
  }
}
```

</td>
      </tr>
      <tr id="BT-109-Lot">
        <td class="field break-all">
            <p><b>BT-109-Lot</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/procedure-lot-part-information.html#frameworkAgreementSection"></a><br>Framework Duration Justification</p><p><i>BT-109:</i> The justification for exceptional cases when the duration of framework agreements exceeds the legal limits. </p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='Lot']/cac:TenderingProcess/cac:FrameworkAgreement/cbc:Justification</span></code>
        </td>
        <td class="mapping">

<a href="operations.md#get-the-lot-for-a-procurementprojectlot">Get the lot for the ProcurementProjectLot</a> and map to its `.techniques.frameworkAgreement.periodRationale`.

```xml
<cac:FrameworkAgreement>
  <cbc:Justification languageID="ENG">The exceptional duration of ...</cbc:Justification>
</cac:FrameworkAgreement>
```

```json
{
  "tender": {
    "lots": [
      {
        "techniques": {
          "frameworkAgreement": {
            "periodRationale": "The exceptional duration of ..."
          }
        }
      }
    ]
  }
}
```

</td>
      </tr>
      <tr id="BT-11-Procedure-Buyer">
        <td class="field break-all">
            <p><b>BT-11-Procedure-Buyer</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/parties.html#_buyer_information"></a><br>Buyer Legal Type</p><p><i>BT-11:</i> The type of buyer according to procurement legislation (e.g. central government authority, body governed by public law, public undertaking).</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ContractingParty/cac:ContractingPartyType/cbc:PartyTypeCode[@listName='buyer-legal-type']</span></code>
        </td>
        <td class="mapping">

- <a href="operations.md#get-the-organization-for-the-buyer">Get the organization for the buyer</a> and add a `Classification` object to its `.details.classifications` array.
- Map the value of this field to the classification's `.id`.
- Look up the code's label in the <a href="https://op.europa.eu/en/web/eu-vocabularies/concept-scheme/-/resource?uri=http://publications.europa.eu/resource/authority/buyer-legal-type">authority table</a> and map it to the classification's `.description`.
- Set the classification's `.scheme` to 'TED_CA_TYPE'.

```xml
<cac:ContractingParty>
  <cac:Party>
    <cac:PartyIdentification>
      <cbc:ID schemeName="organization">ORG-0001</cbc:ID>
    </cac:PartyIdentification>
  </cac:Party>
  <cac:ContractingPartyType>
    <cbc:PartyTypeCode listName="buyer-legal-type">body-pl</cbc:PartyTypeCode>
  </cac:ContractingPartyType>
</cac:ContractingParty>
```

```json
{
  "parties": [
    {
      "id": "ORG-0001",
      "details": {
        "classifications": [
          {
            "scheme": "TED_CA_TYPE",
            "id": "body-pl",
            "description": "Body governed by public law."
          }
        ]
      }
    }
  ]
}
```

</td>
      </tr>
      <tr id="BT-111-Lot">
        <td class="field break-all">
            <p><b>BT-111-Lot</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/procedure-lot-part-information.html#frameworkAgreementSection"></a><br>Framework Buyer Categories</p><p><i>BT-111:</i> Any additional categories of buyers participating in the framework agreement and not mentioned by name (e.g. "all hospitals in the Tuscany region").</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='Lot']/cac:TenderingProcess/cac:FrameworkAgreement/cac:SubsequentProcessTenderRequirement[cbc:Name/text()='buyer-categories']/cbc:Description</span></code>
        </td>
        <td class="mapping">

<a href="operations.md#get-the-lot-for-a-procurementprojectlot">Get the lot for the ProcurementProjectLot</a> and map to the its `.techniques.frameworkAgreement.buyerCategories`.

```xml
<cac:FrameworkAgreement>
  <cac:SubsequentProcessTenderRequirement>
    <cbc:Name>buyer-categories</cbc:Name>
    <cbc:Description languageID="ENG">Offices of the "greater region" ...</cbc:Description>
  </cac:SubsequentProcessTenderRequirement>
</cac:FrameworkAgreement>
```

```json
{
  "tender": {
    "lots": [
      {
        "techniques": {
          "frameworkAgreement": {
            "buyerCategories": "Offices of the \"greater region\" ..."
          }
        }
      }
    ]
  }
}
```

</td>
      </tr>
      <tr id="BT-1118-NoticeResult">
        <td class="field break-all">
            <p><b>BT-1118-NoticeResult</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/competition-results.html#_notice_aggregated_amounts"></a><br>Notice Framework Approximate Value</p><p><i>BT-1118:</i> The approximate value to be spent within the framework agreement(s) announced in this notice over its/their whole duration, in all lots, including options and renewals, as calculated on the basis of the winner’s tender or winners’ tenders.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:NoticeResult/efbc:OverallApproximateFrameworkContractsAmount</span></code>
        </td>
        <td class="mapping">

Discard.

```xml
<efac:NoticeResult>
  <cbc:OverallApproximateFrameworkContractsAmount currencyID="EUR">6000</cbc:OverallApproximateFrameworkContractsAmount>
</efac:NoticeResult>
```



</td>
      </tr>
      <tr id="BT-113-Lot">
        <td class="field break-all">
            <p><b>BT-113-Lot</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/procedure-lot-part-information.html#frameworkAgreementSection"></a><br>Framework Maximum Participants Number</p><p><i>BT-113:</i> The maximum number of participants in the framework agreement.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='Lot']/cac:TenderingProcess/cac:FrameworkAgreement/cbc:MaximumOperatorQuantity</span></code>
        </td>
        <td class="mapping">

<a href="operations.md#get-the-lot-for-a-procurementprojectlot">Get the lot for the ProcurementProjectLot</a> and map to the its  `.techniques.frameworkAgreement.maximumParticipants`.

```xml
<cac:FrameworkAgreement>
  <cbc:MaximumOperatorQuantity>50</cbc:MaximumOperatorQuantity>
</cac:FrameworkAgreement>
```

```json
{
  "tender": {
    "lots": [
      {
        "techniques": {
          "frameworkAgreement": {
            "maximumParticipants": 50
          }
        }
      }
    ]
  }
}
```

</td>
      </tr>
      <tr id="BT-115-Lot">
        <td class="field break-all">
            <p><b>BT-115-Lot</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/procedure-lot-part-information.html#GPASection"></a><br>GPA Coverage</p><p><i>BT-115:</i> The procurement is covered by the Government Procurement Agreement (GPA).</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='Lot']/cac:TenderingProcess/cbc:GovernmentAgreementConstraintIndicator</span></code>
        </td>
        <td class="mapping">

If "true", <a href="operations.md#get-the-lot-for-a-procurementprojectlot">get the lot for the ProcurementProjectLot</a> and add "GPA" to its `.coveredBy` array. Otherwise, discard.

```xml
<cbc:GovernmentAgreementConstraintIndicator>true</cbc:GovernmentAgreementConstraintIndicator>
```

```json
{
  "tender": {
    "lots": [
      {
        "coveredBy": [
          "GPA"
        ]
      }
    ]
  }
}
```

</td>
      </tr>
      <tr id="BT-115-Part">
        <td class="field break-all">
            <p><b>BT-115-Part</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/procedure-lot-part-information.html#GPASection"></a><br>GPA Coverage</p><p><i>BT-115:</i> The procurement is covered by the Government Procurement Agreement (GPA).</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='Part']/cac:TenderingProcess/cbc:GovernmentAgreementConstraintIndicator</span></code>
        </td>
        <td class="mapping">

If "true", add "GPA" to the `tender.coveredBy` array. Otherwise, do nothing.

```xml
<cbc:GovernmentAgreementConstraintIndicator>true</cbc:GovernmentAgreementConstraintIndicator>
```

```json
{
  "tender": {
    "coveredBy": [
      "GPA"
    ]
  }
}
```

</td>
      </tr>
      <tr id="BT-118-NoticeResult">
        <td class="field break-all">
            <p><b>BT-118-NoticeResult</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/competition-results.html#_notice_aggregated_amounts"></a><br>Notice Framework Maximum Value</p><p><i>BT-118:</i> The maximum value which can be spent within the framework agreement(s) announced in this notice over its/their whole duration, in all lots, including options and renewals, as calculated on the basis of the winner’s tender or winners’ tenders.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:NoticeResult/efbc:OverallMaximumFrameworkContractsAmount</span></code>
        </td>
        <td class="mapping">

Discard.

```xml
<efac:NoticeResult>
  <cbc:OverallMaximumFrameworkContractsAmount currencyID="EUR">6000</cbc:OverallMaximumFrameworkContractsAmount>
</efac:NoticeResult>
```



</td>
      </tr>
      <tr id="BT-119-LotResult">
        <td class="field break-all">
            <p><b>BT-119-LotResult</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/competition-results.html#_lot_result"></a><br>Dynamic Purchasing System Termination</p><p><i>BT-119:</i> The dynamic purchasing system is terminated. No further contracts, besides those published in this notice, will be awarded in the dynamic purchasing system. This field can be used even if no contracts are awarded in the contract award notice.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:NoticeResult/efac:LotResult/efbc:DPSTerminationIndicator</span></code>
        </td>
        <td class="mapping">

If "true", <a href="operations.md#get-the-lot-for-a-lotresult">get the lot for the LotResult</a> and set the lot's `.techniques.dynamicPurchasingSystem.status` to 'terminated'. Otherwise, discard.

```xml
<efac:LotResult>
  <efbc:DPSTerminationIndicator>true</efbc:DPSTerminationIndicator>
</efac:LotResult>
```

```json
{
  "tender": {
    "lots": [
      {
        "techniques": {
          "dynamicPurchasingSystem": {
            "status": "terminated"
          }
        }
      }
    ]
  }
}
```

</td>
      </tr>
      <tr id="BT-120-Lot">
        <td class="field break-all">
            <p><b>BT-120-Lot</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/procedure-lot-part-information.html#awardConsequencesSection"></a><br>No Negotiation Necessary</p><p><i>BT-120:</i> The buyer reserves the right to award the contract on the basis of the initial tenders without any further negotiations.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='Lot']/cac:TenderingTerms/cac:AwardingTerms/cbc:NoFurtherNegotiationIndicator</span></code>
        </td>
        <td class="mapping">

<a href="operations.md#get-the-lot-for-a-procurementprojectlot">Get the lot for the ProcurementProjectLot</a> and set its `.secondStage.noNegotiationNecessary` to `true`.

```xml
<cbc:NoFurtherNegotiationIndicator>true</cbc:NoFurtherNegotiationIndicator>
```

```json
{
  "tender": {
    "lots": [
      {
        "secondStage": {
          "noNegotiationNecessary": true
        }
      }
    ]
  }
}
```

</td>
      </tr>
      <tr id="BT-122-Lot">
        <td class="field break-all">
            <p><b>BT-122-Lot</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/procedure-lot-part-information.html#auctionTermsSection"></a><br>Electronic Auction Description</p><p><i>BT-122:</i> Any additional information about the electronic auction.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='Lot']/cac:TenderingProcess/cac:AuctionTerms/cbc:Description</span></code>
        </td>
        <td class="mapping">

<a href="operations.md#get-the-lot-for-a-procurementprojectlot">Get the lot for the ProcurementProjectLot</a> and map to its `.techniques.electronicAuction.description`.

```xml
<cac:AuctionTerms>
  <cbc:Description languageID="ENG">The online auction solution ...</cbc:Description>
</cac:AuctionTerms>
```

```json
{
  "tender": {
    "lots": [
      {
        "techniques": {
          "electronicAuction": {
            "description": "The online auction solution ..."
          }
        }
      }
    ]
  }
}
```

</td>
      </tr>
      <tr id="BT-123-Lot">
        <td class="field break-all">
            <p><b>BT-123-Lot</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/procedure-lot-part-information.html#auctionTermsSection"></a><br>Electronic Auction URL</p><p><i>BT-123:</i> The internet address of the electronic auction.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='Lot']/cac:TenderingProcess/cac:AuctionTerms/cbc:AuctionURI</span></code>
        </td>
        <td class="mapping">

<a href="operations.md#get-the-lot-for-a-procurementprojectlot">Get the lot for the ProcurementProjectLot</a> and map to its `.techniques.electronicAuction.url`.

```xml
<cac:AuctionTerms>
  <cbc:AuctionURI>https://my-online-eauction.eu/</cbc:AuctionURI>
</cac:AuctionTerms>
```

```json
{
  "tender": {
    "lots": [
      {
        "techniques": {
          "electronicAuction": {
            "url": "https://my-online-eauction.eu/"
          }
        }
      }
    ]
  }
}
```

</td>
      </tr>
      <tr id="BT-124-Lot">
        <td class="field break-all">
            <p><b>BT-124-Lot</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/procedure-lot-part-information.html#atypicalToolSection"></a><br>Tool Atypical URL</p><p><i>BT-124:</i> Electronic communication requires the use of tools and devices that are not generally available. The uniform resource locator (e.g. the web address) which gives unrestricted and full direct access to these tools and devices.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='Lot']/cac:TenderingProcess/cbc:AccessToolsURI</span></code>
        </td>
        <td class="mapping">

<a href="operations.md#get-the-lot-for-a-procurementprojectlot">Get the lot for the ProcurementProjectLot</a> and map to its `.communication.atypicalToolUrl`.

```xml
<cbc:AccessToolsURI>https://my-atypical-tool.com/</cbc:AccessToolsURI>
```

```json
{
  "tender": {
    "lots": [
      {
        "communication": {
          "atypicalToolUrl": "https://my-atypical-tool.com/"
        }
      }
    ]
  }
}
```

</td>
      </tr>
      <tr id="BT-124-Part">
        <td class="field break-all">
            <p><b>BT-124-Part</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/procedure-lot-part-information.html#atypicalToolSection"></a><br>Tool Atypical URL</p><p><i>BT-124:</i> Electronic communication requires the use of tools and devices that are not generally available. The uniform resource locator (e.g. the web address) which gives unrestricted and full direct access to these tools and devices.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='Part']/cac:TenderingProcess/cbc:AccessToolsURI</span></code>
        </td>
        <td class="mapping">

Map to `tender.communication.atypicalToolUrl`

```xml
<cbc:AccessToolsURI>https://my-atypical-tool.com/</cbc:AccessToolsURI>
```

```json
{
  "tender": {
    "communication": {
      "atypicalToolUrl": "https://my-atypical-tool.com/"
    }
  }
}
```

</td>
      </tr>
      <tr id="BT-125(i)-Lot">
        <td class="field break-all">
            <p><b>BT-125(i)-Lot</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/procedure-lot-part-information.html#previousPlanningSection"></a><br>Previous Planning Identifier</p><p><i>BT-125:</i> The identifier of a prior information notice or another similar notice related to this notice.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='Lot']/cac:TenderingProcess/cac:NoticeDocumentReference/cbc:ID</span></code>
        </td>
        <td class="mapping">

<a href="operations.md#reference-a-previous-publication">Reference a previous publication</a>

```xml
<cac:NoticeDocumentReference>
  <cbc:ID schemeName="notice-id-ref">123e4567-e89b-12d3-a456-426614174000-06</cbc:ID>
</cac:NoticeDocumentReference>
```

```json
{
  "relatedProcesses": [
    {
      "id": "1",
      "relationship": [
        "planning"
      ],
      "scheme": "eu-oj",
      "identifier": "123e4567-e89b-12d3-a456-426614174000-06"
    }
  ]
}
```

</td>
      </tr>
      <tr id="BT-125(i)-Part">
        <td class="field break-all">
            <p><b>BT-125(i)-Part</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/procedure-lot-part-information.html#previousPlanningSection"></a><br>Previous Planning Identifier</p><p><i>BT-125:</i> The identifier of a prior information notice or another similar notice related to this notice.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='Part']/cac:TenderingProcess/cac:NoticeDocumentReference/cbc:ID</span></code>
        </td>
        <td class="mapping">

Concatenate with <a href="#BT-1251-Part">BT-1251-Part Previous Planning Part Identifier</a> and <a href="operations.md#reference-a-previous-publication">reference a previous publication</a>.

```xml
<cac:NoticeDocumentReference>
  <cbc:ID schemeName="notice-id-ref">123e4567-e89b-12d3-a456-426614174000-06</cbc:ID>
  <cbc:ReferencedDocumentInternalAddress>PAR-0001</cbc:ReferencedDocumentInternalAddress>
</cac:NoticeDocumentReference>
```

```json
{
  "relatedProcesses": [
    {
      "id": "1",
      "relationship": [
        "planning"
      ],
      "scheme": "eu-oj",
      "identifier": "123e4567-e89b-12d3-a456-426614174000-06-PAR-0001"
    }
  ]
}
```

</td>
      </tr>
      <tr id="BT-1251-Lot">
        <td class="field break-all">
            <p><b>BT-1251-Lot</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/procedure-lot-part-information.html#previousPlanningSection"></a><br>Previous Planning Part Identifier</p><p><i>BT-1251:</i> The identifier of a part of a prior information notice or another similar notice related to this notice.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='Lot']/cac:TenderingProcess/cac:NoticeDocumentReference/cbc:ReferencedDocumentInternalAddress</span></code>
        </td>
        <td class="mapping">

This field maps to the same `Related Process` objects as created for BT-125(i)-Lot.

For each `cac:NoticeDocumentReference`, add or update the corresponding `Related Process` object in the `relatedProcesses` array and map to its `relatedLots`.

```xml
<cac:NoticeDocumentReference>
  <cbc:ID>9c0fd704-64d3-4294-a3b6-6df45911ab9f-01</cbc:ID>
  <cbc:ReferencedDocumentInternalAddress>123</cbc:ReferencedDocumentInternalAddress>
</cac:NoticeDocumentReference>
```

```json
{
  "relatedProcesses": [
    {
      "id": "1",
      "relationship": [
        "planning"
      ],
      "scheme": "eu-oj",
      "identifier": "9c0fd704-64d3-4294-a3b6-6df45911ab9f-01",
      "relatedLots": [
        "123"
      ]
    }
  ]
}
```

</td>
      </tr>
      <tr id="BT-1251-Part">
        <td class="field break-all">
            <p><b>BT-1251-Part</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/procedure-lot-part-information.html#previousPlanningSection"></a><br>Previous Planning Part Identifier</p><p><i>BT-1251:</i> The identifier of a part of a prior information notice or another similar notice related to this notice.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='Part']/cac:TenderingProcess/cac:NoticeDocumentReference/cbc:ReferencedDocumentInternalAddress</span></code>
        </td>
        <td class="mapping">

Concatenate with <a href="#BT-125(i)-Part">BT-125(i)-Part Previous Planning Identifier</a> and <a href="operations.md#reference-a-previous-publication">reference a previous publication</a>.

```xml
<cac:NoticeDocumentReference>
  <cbc:ID schemeName="notice-id-ref">123e4567-e89b-12d3-a456-426614174000-06</cbc:ID>
  <cbc:ReferencedDocumentInternalAddress>PAR-0001</cbc:ReferencedDocumentInternalAddress>
</cac:NoticeDocumentReference>
```

```json
{
  "relatedProcesses": [
    {
      "id": "1",
      "relationship": [
        "planning"
      ],
      "scheme": "eu-oj",
      "identifier": "123e4567-e89b-12d3-a456-426614174000-06-PAR-0001"
    }
  ]
}
```

</td>
      </tr>
      <tr id="BT-1252-Procedure">
        <td class="field break-all">
            <p><b>BT-1252-Procedure</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/procedure-lot-part-information.html#directAwardSection"></a><br>Direct Award Justification Previous Procedure Identifier</p><p><i>BT-1252:</i> An identifier of a previous procedure that justifies the use of a procedure which allows directly awarding contracts, i.e. justifying a procedure that does not require publishing a call for competition in the Official Journal of the European Union.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:TenderingProcess/cac:ProcessJustification[cbc:ProcessReasonCode/@listName='direct-award-justification']/cbc:Description</span></code>
        </td>
        <td class="mapping">

Add a `RelatedProcess` object to the `relatedProcesses` array and set its .id (string) sequentially across all notices for this procedure.

For example, if a first notice for a given procedure has nine related processes, it uses id's "1" through "9". A second notice for the same procedure then uses id's "10" and up, etc.

Map the value of the field to `.identifier`. Set `.scheme` to "eu-oj". If the value of `sibling::cbc:ProcessReasonCode` is "irregular" or "unsuitable", add 'unsuccessfulProcess' to the `.relationship` array. If it is "additional", "existing" or "repetition, add 'prior' to the `.relationship` array.

```xml
<cac:ProcessJustification>
  <cbc:Description>123e4567-e89b-12d3-a456-426614174000</cbc:Description>
</cac:ProcessJustification>
```

```json
{
  "relatedProcesses": [
    {
      "id": "1",
      "identifier": "123e4567-e89b-12d3-a456-426614174000",
      "scheme": "eu-oj",
      "relationship": [
        "prior"
      ]
    }
  ]
}
```

</td>
      </tr>
      <tr id="BT-127-notice">
        <td class="field break-all">
            <p><b>BT-127-notice</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/notice-information.html#futureNoticeSection"></a><br>Future Notice</p><p><i>BT-127:</i> The estimated date of publication of a contract notice within this procedure.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cbc:PlannedDate</span></code>
        </td>
        <td class="mapping">

<a href="operations.md#convert-a-date-to-iso-format">Convert date to ISO format</a> and map to `tender.communication.futureNoticeDate`.

```xml
<cbc:PlannedDate>2020-03-15+01:00</cbc:PlannedDate>
```

```json
{
  "tender": {
    "communication": {
      "futureNoticeDate": "2020-03-15T00:00:00+01:00"
    }
  }
}
```

</td>
      </tr>
      <tr id="BT-13(d)-Lot">
        <td class="field break-all">
            <p><b>BT-13(d)-Lot</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/procedure-lot-part-information.html#additionalInfoDeadlineSection"></a><br>Additional Information Deadline</p><p><i>BT-13:</i> The time limit for requesting additional information about the procurement procedure.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='Lot']/cac:TenderingProcess/cac:AdditionalInformationRequestPeriod/cbc:EndDate</span></code>
        </td>
        <td class="mapping">

<a href="operations.md#get-the-lot-for-a-procurementprojectlot">Get the lot for the ProcurementProjectLot</a>, combine with <a href="#BT-13(t)-lot">BT-13(t)-Lot</a>, <a href="operations.md#convert-a-date-to-iso-format">convert date to ISO format</a> and map to the lot's `.enquiryPeriod.endDate`.

```xml
<cac:AdditionalInformationRequestPeriod>
  <cbc:EndDate>2019-11-08+01:00</cbc:EndDate>
</cac:AdditionalInformationRequestPeriod>
```

```json
{
  "tender": {
    "lots": [
      {
        "enquiryPeriod": {
          "endDate": "2019-11-08T23:59:59+01:00"
        }
      }
    ]
  }
}
```

</td>
      </tr>
      <tr id="BT-13(d)-Part">
        <td class="field break-all">
            <p><b>BT-13(d)-Part</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/procedure-lot-part-information.html#additionalInfoDeadlineSection"></a><br>Additional Information Deadline</p><p><i>BT-13:</i> The time limit for requesting additional information about the procurement procedure.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='Part']/cac:TenderingProcess/cac:AdditionalInformationRequestPeriod/cbc:EndDate</span></code>
        </td>
        <td class="mapping">

Combine with <a href="#BT-13(t)-part">BT-13(t)-Part</a>, <a href="operations.md#convert-a-date-to-iso-format">convert date to ISO format</a> and map to `tender.enquiryPeriod.endDate`.

```xml
<cac:AdditionalInformationRequestPeriod>
  <cbc:EndDate>2019-11-08+01:00</cbc:EndDate>
</cac:AdditionalInformationRequestPeriod>
```

```json
{
  "tender": {
    "enquiryPeriod": {
      "endDate": "2019-11-08T23:59:59+01:00"
    }
  }
}
```

</td>
      </tr>
      <tr id="BT-13(t)-Lot">
        <td class="field break-all">
            <p><b>BT-13(t)-Lot</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/procedure-lot-part-information.html#additionalInfoDeadlineSection"></a><br>Additional Information Deadline</p><p><i>BT-13:</i> The time limit for requesting additional information about the procurement procedure.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='Lot']/cac:TenderingProcess/cac:AdditionalInformationRequestPeriod/cbc:EndTime</span></code>
        </td>
        <td class="mapping">

<a href="operations.md#get-the-lot-for-a-procurementprojectlot">Get the lot for the ProcurementProjectLot</a>, combine with <a href="#BT-13(d)-lot">BT-13(d)-Lot</a>, <a href="operations.md#convert-a-date-to-iso-format">convert date to ISO format</a> and map to the lot's `.enquiryPeriod.endDate`.

```xml
<cac:AdditionalInformationRequestPeriod>
  <cbc:EndTime>18:00:00+01:00</cbc:EndTime>
</cac:AdditionalInformationRequestPeriod>
```

```json
{
  "tender": {
    "lots": [
      {
        "enquiryPeriod": {
          "endDate": "2019-11-08T18:00:00+01:00"
        }
      }
    ]
  }
}
```

</td>
      </tr>
      <tr id="BT-13(t)-Part">
        <td class="field break-all">
            <p><b>BT-13(t)-Part</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/procedure-lot-part-information.html#additionalInfoDeadlineSection"></a><br>Additional Information Deadline</p><p><i>BT-13:</i> The time limit for requesting additional information about the procurement procedure.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='Part']/cac:TenderingProcess/cac:AdditionalInformationRequestPeriod/cbc:EndTime</span></code>
        </td>
        <td class="mapping">

Combine with <a href="#BT-13(d)-part">BT-13(d)-Part</a>, <a href="operations.md#convert-a-date-to-iso-format">convert date to ISO format</a> and map to `tender.enquiryPeriod.endDate`.

```xml
<cac:AdditionalInformationRequestPeriod>
  <cbc:EndTime>18:00:00+01:00</cbc:EndTime>
</cac:AdditionalInformationRequestPeriod>
```

```json
{
  "tender": {
    "enquiryPeriod": {
      "endDate": "2019-11-08T18:00:00+01:00"
    }
  }
}
```

</td>
      </tr>
      <tr id="BT-130-Lot">
        <td class="field break-all">
            <p><b>BT-130-Lot</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/procedure-lot-part-information.html#tenderInvitationSection"></a><br>Dispatch Invitation Tender</p><p><i>BT-130:</i> The estimated date of dispatch of the invitations to submit tenders in two (or more) stage procedures.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='Lot']/cac:TenderingProcess/cac:InvitationSubmissionPeriod/cbc:StartDate</span></code>
        </td>
        <td class="mapping">

<a href="operations.md#get-the-lot-for-a-procurementprojectlot">Get the lot for the ProcurementProjectLot</a>, <a href="operations.md#convert-a-date-to-iso-format">convert date to ISO format</a> and map to the lot's `.secondStage.invitationDate`.

```xml
<cac:InvitationSubmissionPeriod>
  <cbc:StartDate>2019-11-15+01:00</cbc:StartDate>
</cac:InvitationSubmissionPeriod>
```

```json
{
  "tender": {
    "lots": [
      {
        "secondStage": {
          "invitationDate": "2019-11-15T00:00:00+01:00"
        }
      }
    ]
  }
}
```

</td>
      </tr>
      <tr id="BT-131(d)-Lot">
        <td class="field break-all">
            <p><b>BT-131(d)-Lot</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/procedure-lot-part-information.html#tendersDeadlineSection"></a><br>Deadline Receipt Tenders</p><p><i>BT-131:</i> The time limit for receipt of tenders.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='Lot']/cac:TenderingProcess/cac:TenderSubmissionDeadlinePeriod/cbc:EndDate</span></code>
        </td>
        <td class="mapping">

<a href="operations.md#get-the-lot-for-a-procurementprojectlot">Get the lot for the ProcurementProjectLot</a>, combine with <a href="#BT-131(t)-lot">BT-131(t)-Lot</a>, <a href="operations.md#convert-a-date-to-iso-format">convert date to ISO format</a> and map to the lot's `.tenderPeriod.endDate`.

```xml
<cac:TenderSubmissionDeadlinePeriod>
  <cbc:EndDate>2019-11-30+01:00</cbc:EndDate>
</cac:TenderSubmissionDeadlinePeriod>
```

```json
{
  "tender": {
    "lots": [
      {
        "tenderPeriod": {
          "endDate": "2019-11-30T23:59:59+01:00"
        }
      }
    ]
  }
}
```

</td>
      </tr>
      <tr id="BT-131(t)-Lot">
        <td class="field break-all">
            <p><b>BT-131(t)-Lot</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/procedure-lot-part-information.html#tendersDeadlineSection"></a><br>Deadline Receipt Tenders</p><p><i>BT-131:</i> The time limit for receipt of tenders.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='Lot']/cac:TenderingProcess/cac:TenderSubmissionDeadlinePeriod/cbc:EndTime</span></code>
        </td>
        <td class="mapping">

<a href="operations.md#get-the-lot-for-a-procurementprojectlot">Get the lot for the ProcurementProjectLot</a>, combine with <a href="#BT-131(d)-lot">BT-131(d)-Lot</a>, <a href="operations.md#convert-a-date-to-iso-format">convert date to ISO format</a> and map to the lot's `.tenderPeriod.endDate`.

```xml
<cac:TenderSubmissionDeadlinePeriod>
  <cbc:EndTime>12:00:00+01:00</cbc:EndTime>
</cac:TenderSubmissionDeadlinePeriod>
```

```json
{
  "tender": {
    "lots": [
      {
        "tenderPeriod": {
          "endDate": "2019-11-30T12:00:00+01:00"
        }
      }
    ]
  }
}
```

</td>
      </tr>
      <tr id="BT-1311(d)-Lot">
        <td class="field break-all">
            <p><b>BT-1311(d)-Lot</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/procedure-lot-part-information.html#requestDeadlineSection"></a><br>Deadline Receipt Requests</p><p><i>BT-1311:</i> The time limit for receipt of requests to participate.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='Lot']/cac:TenderingProcess/cac:ParticipationRequestReceptionPeriod/cbc:EndDate</span></code>
        </td>
        <td class="mapping">

<a href="operations.md#get-the-lot-for-a-procurementprojectlot">Get the lot for the ProcurementProjectLot</a>, combine with <a href="#BT-1311(t)-lot">BT-1311(t)-Lot</a>, <a href="operations.md#convert-a-date-to-iso-format">convert date to ISO format</a> and map to the lot's `.tenderPeriod.endDate`.

```xml
<cac:ParticipationRequestReceptionPeriod>
  <cbc:EndDate>2019-11-25+01:00</cbc:EndDate>
</cac:ParticipationRequestReceptionPeriod>
```

```json
{
  "tender": {
    "lots": [
      {
        "tenderPeriod": {
          "endDate": "2019-11-25T23:59:59+01:00"
        }
      }
    ]
  }
}
```

</td>
      </tr>
      <tr id="BT-1311(t)-Lot">
        <td class="field break-all">
            <p><b>BT-1311(t)-Lot</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/procedure-lot-part-information.html#requestDeadlineSection"></a><br>Deadline Receipt Requests</p><p><i>BT-1311:</i> The time limit for receipt of requests to participate.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='Lot']/cac:TenderingProcess/cac:ParticipationRequestReceptionPeriod/cbc:EndTime</span></code>
        </td>
        <td class="mapping">

<a href="operations.md#get-the-lot-for-a-procurementprojectlot">Get the lot for the ProcurementProjectLot</a>, combine with <a href="#BT-1311(d)-lot">BT-1311(d)-Lot</a>, <a href="operations.md#convert-a-date-to-iso-format">convert date to ISO format</a> and map to the lot's `.tenderPeriod.endDate`.

```xml
<cac:ParticipationRequestReceptionPeriod>
  <cbc:EndTime>12:00:00+01:00</cbc:EndTime>
</cac:ParticipationRequestReceptionPeriod>
```

```json
{
  "tender": {
    "lots": [
      {
        "tenderPeriod": {
          "endDate": "2019-11-25T12:00:00+01:00"
        }
      }
    ]
  }
}
```

</td>
      </tr>
      <tr id="BT-132(d)-Lot">
        <td class="field break-all">
            <p><b>BT-132(d)-Lot</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/procedure-lot-part-information.html#openingEventSection"></a><br>Public Opening Date</p><p><i>BT-132:</i> The date and time for the public opening of tenders.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='Lot']/cac:TenderingProcess/cac:OpenTenderEvent/cbc:OccurrenceDate</span></code>
        </td>
        <td class="mapping">

<a href="operations.md#get-the-lot-for-a-procurementprojectlot">Get the lot for the ProcurementProjectLot</a>, combine with <a href="#BT-132(t)-lot">BT-132(t)-Lot</a>, <a href="operations.md#convert-a-date-to-iso-format">convert date to ISO format</a> and map to the lot's `.awardPeriod.startDate` and to its `.bidOpening.date`.

```xml
<cac:OpenTenderEvent>
  <cbc:OccurrenceDate>2019-11-05+01:00</cbc:OccurrenceDate>
</cac:OpenTenderEvent>
```

```json
{
  "tender": {
    "lots": [
      {
        "awardPeriod": {
          "startDate": "2019-11-05T00:00:00+01:00"
        }
      }
    ]
  }
}
```

</td>
      </tr>
      <tr id="BT-132(t)-Lot">
        <td class="field break-all">
            <p><b>BT-132(t)-Lot</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/procedure-lot-part-information.html#openingEventSection"></a><br>Public Opening Date</p><p><i>BT-132:</i> The date and time for the public opening of tenders.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='Lot']/cac:TenderingProcess/cac:OpenTenderEvent/cbc:OccurrenceTime</span></code>
        </td>
        <td class="mapping">

<a href="operations.md#get-the-lot-for-a-procurementprojectlot">Get the lot for the ProcurementProjectLot</a>, combine with <a href="#BT-132(d)-lot">BT-132(d)-Lot</a>, <a href="operations.md#convert-a-date-to-iso-format">convert date to ISO format</a> and map to the lot's `.awardPeriod.startDate` and to its `.bidOpening.date`.

```xml
<cac:OpenTenderEvent>
  <cbc:OccurrenceTime>14:00:00+01:00</cbc:OccurrenceTime>
</cac:OpenTenderEvent>
```

```json
{
  "tender": {
    "lots": [
      {
        "awardPeriod": {
          "startDate": "2019-11-05T14:00:00+01:00"
        }
      }
    ]
  }
}
```

</td>
      </tr>
      <tr id="BT-133-Lot">
        <td class="field break-all">
            <p><b>BT-133-Lot</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/procedure-lot-part-information.html#openingEventSection"></a><br>Public Opening Place</p><p><i>BT-133:</i> The place (e.g. physical address, URL) where the tenders will be publicly opened.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='Lot']/cac:TenderingProcess/cac:OpenTenderEvent/cac:OccurenceLocation/cbc:Description</span></code>
        </td>
        <td class="mapping">

<a href="operations.md#get-the-lot-for-a-procurementprojectlot">Get the lot for the ProcurementProjectLot</a> and map to its `.bidOpening.location.description`.

```xml
<cac:OpenTenderEvent>
  <cac:OccurenceLocation>
    <cbc:Description languageID="ENG">online at URL https://event-on-line.org/d22f65 ...</cbc:Description>
  </cac:OccurenceLocation>
</cac:OpenTenderEvent>
```

```json
{
  "tender": {
    "lots": [
      {
        "bidOpening": {
          "location": {
            "description": "online at URL https://event-on-line.org/d22f65 ..."
          }
        }
      }
    ]
  }
}
```

</td>
      </tr>
      <tr id="BT-134-Lot">
        <td class="field break-all">
            <p><b>BT-134-Lot</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/procedure-lot-part-information.html#openingEventSection"></a><br>Public Opening Description</p><p><i>BT-134:</i> Further information about the public opening of tenders. (For example, who may participate in the opening and whether any authorisation is needed.)</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='Lot']/cac:TenderingProcess/cac:OpenTenderEvent/cbc:Description</span></code>
        </td>
        <td class="mapping">

<a href="operations.md#get-the-lot-for-a-procurementprojectlot">Get the lot for the ProcurementProjectLot</a> and map to its `bidOpening.description`.

```xml
<cac:OpenTenderEvent>
  <cbc:Description languageID="ENG">Any tenderer may attend ...</cbc:Description>
</cac:OpenTenderEvent>
```

```json
{
  "tender": {
    "lots": [
      {
        "bidOpening": {
          "description": "Any tenderer may attend ..."
        }
      }
    ]
  }
}
```

</td>
      </tr>
      <tr id="BT-135-Procedure">
        <td class="field break-all">
            <p><b>BT-135-Procedure</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/procedure-lot-part-information.html#directAwardSection"></a><br>Direct Award Justification Text</p><p><i>BT-135:</i> The justification for using a procedure which allows directly awarding contracts, i.e. a procedure that does not require publishing a call for competition in the Official Journal of the European Union.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:TenderingProcess/cac:ProcessJustification[cbc:ProcessReasonCode/@listName='direct-award-justification']/cbc:ProcessReason</span></code>
        </td>
        <td class="mapping">

Map to `tender.procurementMethodRationale`

```xml
<cac:ProcessJustification>
  <cbc:ProcessReason languageID="ENG">Direct award is justified ...</cbc:ProcessReason>
</cac:ProcessJustification>
```

```json
{
  "tender": {
    "procurementMethodRationale": "Direct award is justified ..."
  }
}
```

</td>
      </tr>
      <tr id="BT-1351-Procedure">
        <td class="field break-all">
            <p><b>BT-1351-Procedure</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/procedure-lot-part-information.html#acceleratedProcedureSection"></a><br>Procedure Accelerated Justification</p><p><i>BT-1351:</i> The justification for using an accelerated procedure.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:TenderingProcess/cac:ProcessJustification[cbc:ProcessReasonCode/@listName='accelerated-procedure']/cbc:ProcessReason</span></code>
        </td>
        <td class="mapping">

Map to `tender.procedure.acceleratedRationale`.

```{seealso}
<a href="#BT-106-Procedure">BT-106-Procedure</a>
```

```xml
<cac:ProcessJustification>
  <cbc:ProcessReasonCode listName="accelerated-procedure">true</cbc:ProcessReasonCode>
  <cbc:ProcessReason languageID="ENG">Direct award is justified ...</cbc:ProcessReason>
</cac:ProcessJustification>
```

```json
{
  "tender": {
    "procedure": {
      "acceleratedRationale": "Direct award is justified ..."
    }
  }
}
```

</td>
      </tr>
      <tr id="BT-136-Procedure">
        <td class="field break-all">
            <p><b>BT-136-Procedure</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/procedure-lot-part-information.html#directAwardSection"></a><br>Direct Award Justification Code</p><p><i>BT-136:</i> A justification for using a procedure which allows directly awarding contracts, i.e. a procedure that does not require publishing a call for competition in the Official Journal of the European Union.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:TenderingProcess/cac:ProcessJustification[cbc:ProcessReasonCode/@listName='direct-award-justification']/cbc:ProcessReasonCode</span></code>
        </td>
        <td class="mapping">

Add a `Classification` object to `tender.procurementMethodRationaleClassifications`, and:

- Map the code to its `.id`.
- Look up the code's label in the <a href="https://op.europa.eu/en/web/eu-vocabularies/concept-scheme/-/resource?uri=http://publications.europa.eu/resource/authority/direct-award-justification">authority table</a> and map it to `.description`.
- Set `.scheme` to its 'eforms-direct-award-justification'.

```xml
<cac:ProcessJustification>
  <cbc:ProcessReasonCode listName="direct-award-justification">ecom-excl</cbc:ProcessReasonCode>
</cac:ProcessJustification>
```

```json
{
  "tender": {
    "procurementMethodRationaleClassifications": [
      {
        "id": "ecom-excl",
        "description": "Specific exclusion in the field of electronic communications",
        "scheme": "eforms-direct-award-justification"
      }
    ]
  }
}
```

</td>
      </tr>
      <tr id="BT-137-Lot">
        <td class="field break-all">
            <p><b>BT-137-Lot</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/procedure-lot-part-information.html#_introduction"></a><br>Purpose Lot Identifier</p><p><i>BT-137:</i> The identifier of a lot. In case of PINs used only for information, the identifier of a part of the notice that may later become a lot or a self-standing procedure. The information in the purpose section refers to this lot or part.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='Lot']/cbc:ID</span></code>
        </td>
        <td class="mapping">

If there is a `Lot` in `tender.lots` whose `.id` is equal to the value of this field, discard. Otherwise, add a `Lot` to `tender.lots` and map to its `.id`.

```xml
<cac:ProcurementProjectLot>
  <cbc:ID schemeName="Lot">LOT-0001</cbc:ID>
</cac:ProcurementProjectLot>
```

```json
{
  "tender": {
    "lots": [
      {
        "id": "LOT-0001"
      }
    ]
  }
}
```

</td>
      </tr>
      <tr id="BT-137-LotsGroup">
        <td class="field break-all">
            <p><b>BT-137-LotsGroup</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/procedure-lot-part-information.html#_introduction"></a><br>Purpose Lot Identifier</p><p><i>BT-137:</i> The identifier of a lot. In case of PINs used only for information, the identifier of a part of the notice that may later become a lot or a self-standing procedure. The information in the purpose section refers to this lot or part.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='LotsGroup']/cbc:ID</span></code>
        </td>
        <td class="mapping">

If there is a `LotGroup` in `tender.lotGroups` whose `.id` is equal to the value of this field, discard. Otherwise, add a `LotGroup` to `tender.lotGroups` and map to its `.id`.

```xml
<cac:ProcurementProjectLot>
  <cbc:ID schemeName="LotsGroup">GLO-0001</cbc:ID>
</cac:ProcurementProjectLot>
```

```json
{
  "tender": {
    "lotGroups": [
      {
        "id": "GLO-0001"
      }
    ]
  }
}
```

</td>
      </tr>
      <tr id="BT-137-Part">
        <td class="field break-all">
            <p><b>BT-137-Part</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/procedure-lot-part-information.html#_introduction"></a><br>Purpose Lot Identifier</p><p><i>BT-137:</i> The identifier of a lot. In case of PINs used only for information, the identifier of a part of the notice that may later become a lot or a self-standing procedure. The information in the purpose section refers to this lot or part.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='Part']/cbc:ID</span></code>
        </td>
        <td class="mapping">

Map to `tender.id`.

```xml
<cac:ProcurementProjectLot>
  <cbc:ID schemeName="Part">PAR-0000</cbc:ID>
</cac:ProcurementProjectLot>
```

```json
{
  "tender": {
    "id": "PAR-0000"
  }
}
```

</td>
      </tr>
      <tr id="BT-13713-LotResult">
        <td class="field break-all">
            <p><b>BT-13713-LotResult</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/competition-results.html#_lot_result"></a><br>Result Lot Identifier</p><p><i>BT-13713:</i> An identifier of a lot. The information in the procedure lot result section refers to this lot.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:NoticeResult/efac:LotResult/efac:TenderLot/cbc:ID</span></code>
        </td>
        <td class="mapping">

Get the `Award` in `awards` whose `.id` is equal to the value of `ancestor::efac:LotResult/cbcID`. If none exists yet:

- Add an `Award` to `awards`.
- Set its `.id` to the value of `ancestor::efac:LotResult/cbc:ID`.

If not already present, add the value of the field to the award's `.relatedLots`

```xml
<efac:TenderLot>
  <cbc:ID schemeName="Lot">LOT-0001</cbc:ID>
</efac:TenderLot>
```

```json
{
  "awards": [
    {
      "id": "RES-0002",
      "relatedLots": [
        "LOT-0001"
      ]
    }
  ]
}
```

</td>
      </tr>
      <tr id="BT-13714-Tender">
        <td class="field break-all">
            <p><b>BT-13714-Tender</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/competition-results.html#lotTenderSection"></a><br>Tender Lot Identifier</p><p><i>BT-13714:</i> An identifier of a lot or a group of lots for which the tender was submitted. The information in the tender section refers to this lot.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:NoticeResult/efac:LotTender/efac:TenderLot/cbc:ID</span></code>
        </td>
        <td class="mapping">

Get the `Bid` in `bids` whose `.id` is equal to the value of `ancestor::efac:LotTender/cbcID`. If none exists yet:

- Add a `Bid` to `bids`.
- Set its `.id` to the value of `ancestor::efac:LotTender/cbc:ID`.

If not already present, add the value of the field to the bid's `.relatedLots`.

```xml
<efac:TenderLot>
  <cbc:ID schemeName="Lot">LOT-0001</cbc:ID>
</efac:TenderLot>
```

```json
{
  "bids": {
    "details": [
      {
        "id": "TEN-0001",
        "relatedLots": [
          "LOT-0001"
        ]
      }
    ]
  }
}
```

</td>
      </tr>
      <tr id="BT-13716-notice">
        <td class="field break-all">
            <p><b>BT-13716-notice</b> <br>Change Previous Section Identifier</p><p><i>BT-13716:</i> An identifier of one or more sections within the changed notice. The information in the change section refers to this section or these sections.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:Changes/efac:Change/efbc:ChangedSectionIdentifier</span></code>
        </td>
        <td class="mapping">

Discard





</td>
      </tr>
      <tr id="BT-1375-Procedure">
        <td class="field break-all">
            <p><b>BT-1375-Procedure</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/procedure-lot-part-information.html#maxLotsSection"></a><br>Group Lot Identifier</p><p><i>BT-1375:</i> An identifier of a lot within the procedure that is part of a group of lots for which one tender can be submitted and evaluated.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:TenderingTerms/cac:LotDistribution/cac:LotsGroup/cac:ProcurementProjectLotReference/cbc:ID[@schemeName='Lot']</span></code>
        </td>
        <td class="mapping">

Get the `LotGroup` in `tender.lotGroups` whose `id` is equal to the value of `ancestor::cac:LotsGroup/cbc:LotsGroupID`. If none exists yet:

- Add a `LotGroup` to `tender.lotGroups`.
- Set its `id` to the value of `ancestor::cac:LotsGroup/cbc:LotsGroupID`.

If not already present, add the value of the field to the lot group's `.relatedLots`.

```xml
<cac:LotDistribution>
  <cac:LotsGroup>
    <cac:ProcurementProjectLotReference>
      <cbc:ID schemeName="Lot">LOT-0002</cbc:ID>
    </cac:ProcurementProjectLotReference>
  </cac:LotsGroup>
</cac:LotDistribution>
```

```json
{
  "tender": {
    "lotGroups": [
      {
        "relatedLots": [
          "LOT-0002"
        ]
      }
    ]
  }
}
```

</td>
      </tr>
      <tr id="BT-14-Lot">
        <td class="field break-all">
            <p><b>BT-14-Lot</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/procedure-lot-part-information.html#procurementDocsSection"></a><br>Documents Restricted</p><p><i>BT-14:</i> The access to certain procurement documents is restricted.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='Lot']/cac:TenderingTerms/cac:CallForTendersDocumentReference/cbc:DocumentType</span></code>
        </td>
        <td class="mapping">

This field maps to the same `ParticipationFee` objects as created for BT-615-Lot and BT-707-Lot.

<a href="operations.md#get-the-lot-for-a-procurementprojectlot">Get the lot for the ProcurementProjectLot</a>.

For each `cac:CallForTendersDocumentReference`, add or update the corresponding `ParticipationFee` object in the lot's `participationFees` array, and:

- Set its `.type` to 'document'.
- Map `cac:CallForTendersDocumentReference/cdc:ID` to its `.id`.

```xml
<cac:CallForTendersDocumentReference>
  <cbc:DocumentType>restricted-document</cbc:DocumentType>
</cac:CallForTendersDocumentReference>
```

```json
{
  "tender": {
    "lots": [
      {
        "participationFees": [
          {
            "id": "1",
            "type": "document"
          }
        ]
      }
    ]
  }
}
```

</td>
      </tr>
      <tr id="BT-14-Part">
        <td class="field break-all">
            <p><b>BT-14-Part</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/procedure-lot-part-information.html#procurementDocsSection"></a><br>Documents Restricted</p><p><i>BT-14:</i> The access to certain procurement documents is restricted.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='Part']/cac:TenderingTerms/cac:CallForTendersDocumentReference/cbc:DocumentType</span></code>
        </td>
        <td class="mapping">

This field maps to the same `ParticipationFee` objects as created for BT-615-Lot and BT-707-Lot.
For each `cac:CallForTendersDocumentReference`, add or update the corresponding `ParticipationFee` object in the `tender.participationFees` array and:

- Set its `.type` to 'document'.
- Map `cac:CallForTendersDocumentReference/cdc:ID` to its `.id`.

```xml
<cac:CallForTendersDocumentReference>
  <cbc:DocumentType>restricted-document</cbc:DocumentType>
</cac:CallForTendersDocumentReference>
```

```json
{
  "tender": {
    "participationFees": [
      {
        "id": "1",
        "type": [
          "document"
        ]
      }
    ]
  }
}
```

</td>
      </tr>
      <tr id="BT-140-notice">
        <td class="field break-all">
            <p><b>BT-140-notice</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/change-notice.html#changeSection"></a><br>Change Reason Code</p><p><i>BT-140:</i> The main reason for the change in the notice compared to the original notice.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:Changes/efac:ChangeReason/cbc:ReasonCode</span></code>
        </td>
        <td class="mapping">

For each `ancestor::efac:Changes/efac:Change`:

- If the change's `/efbc:ChangedSectionIdentifier` (BT-13716) references a LotResult (`RES-XXXX`), <a href="operations.md#get-the-award-for-a-lotresult">get the award for the LotResult</a> and add an `Amendment` object to the award's `.amendments` array. Otherwise, add an `Amendment` object to the `tender.amendments` array.
- If the change's `/efbc:ChangedSectionIdentifier` (BT-13716) references a Lot (`LOT-XXXX`), add an `Amendment` object to the `tender.amendments` array and add the Lot's identifier to the amendment's `.relatedLots` array.
- If the change's `/efbc:ChangedSectionIdentifier` (BT-13716) references a LotsGroup (`GLO-XXXX`), add an `Amendment` object to the `tender.amendments` array and add the LotGroup's identifier to the amendment's `.relatedLotGroups` array.
- Set the amendment's `.id` sequentially across all notices for this procedure. For example, if the first change notice for a procedure has three changes, it uses `id`'s "1" through "3". A second change notice for the same procedure then uses `id`'s "4" and up, etc.
- Add a `Classification` object to the amendment's `rationaleClassifications` array and map the value of this field to its `.id`.
- Look up the code's label in the <a href="https://op.europa.eu/en/web/eu-vocabularies/concept-scheme/-/resource?uri=http://publications.europa.eu/resource/authority/change-corrig-justification">authority table</a> and map it to the classification's `.description`.
- Set the classification's `.scheme` to 'change-corrig-justification'.

```xml
<efac:Changes>
  <efac:Change>
    <efbc:ChangedSectionIdentifier>LOT-0001</efbc:ChangedSectionIdentifier>
  </efac:Change>
  <efac:Change>
    <efbc:ChangedSectionIdentifier>LOT-0002</efbc:ChangedSectionIdentifier>
  </efac:Change>
  <efac:ChangeReason>
    <cbc:ReasonCode listName="change-corrig-justification">update-add</cbc:ReasonCode>
  </efac:ChangeReason>
</efac:Changes>
```

```json
{
  "tender": {
    "amendments": [
      {
        "relatedLots": [
          "LOT-0001"
        ],
        "id": "1",
        "rationaleClassifications": [
          {
            "id": "update-add",
            "description": "Information updated",
            "scheme": "change-corrig-justification"
          }
        ]
      },
      {
        "relatedLots": [
          "LOT-0002"
        ],
        "id": "2",
        "rationaleClassifications": [
          {
            "id": "update-add",
            "description": "Information updated",
            "scheme": "change-corrig-justification"
          }
        ]
      }
    ]
  }
}
```

</td>
      </tr>
      <tr id="BT-141(a)-notice">
        <td class="field break-all">
            <p><b>BT-141(a)-notice</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/change-notice.html#changeSection"></a><br>Change Description</p><p><i>BT-141:</i> The description of changes in the notice compared to the original notice.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:Changes/efac:Change/efbc:ChangeDescription</span></code>
        </td>
        <td class="mapping">

These values map to the same `Amendment` objects as created for BT-140. Update the corresponding `Amendment` object and map to its `.description`.

```xml
<efac:Change>
  <efbc:ChangeDescription languageID="ENG">The changes have been applied to ...</efbc:ChangeDescription>
</efac:Change>
```

```json
{
  "tender": {
    "amendments": [
      {
        "description": "The changes have been applied to..."
      }
    ]
  }
}
```

</td>
      </tr>
      <tr id="BT-142-LotResult">
        <td class="field break-all">
            <p><b>BT-142-LotResult</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/competition-results.html#_lot_result"></a><br>Winner Chosen</p><p><i>BT-142:</i> Whether a winner was chosen. </p>
            <code class="docutils literal notranslate"><span class="pre">/*/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:NoticeResult/efac:LotResult/cbc:TenderResultCode</span></code>
        </td>
        <td class="mapping">

If `open-nw`, <a href="operations.md#get-the-lot-for-a-lotresult">get the lot for the LotResult</a> and set its `.status` to `active`.

Otherwise, <a href="operations.md#get-the-award-for-a-lotresult">get the award for the LotResult</a>, and:

- If `selec-w`, set the awards's `.status` to 'active'.
- If `clos-nw`, set the awards's `.status` to 'unsuccessful'.

Look up the code's label in the <a href="https://op.europa.eu/en/web/eu-vocabularies/concept-scheme/-/resource?uri=http://publications.europa.eu/resource/authority/winner-selection-status">authority table</a> and map it to `.statusDetails`.

```xml
<efac:LotResult>
  <cbc:TenderResultCode listName="winner-selection-status">selec-w</cbc:TenderResultCode>
</efac:LotResult>
```

```json
{
  "awards": [
    {
      "status": "active",
      "statusDetails": "At least one winner was chosen."
    }
  ]
}
```

</td>
      </tr>
      <tr id="BT-144-LotResult">
        <td class="field break-all">
            <p><b>BT-144-LotResult</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/competition-results.html#_lot_result"></a><br>Not Awarded Reason</p><p><i>BT-144:</i> The reason for not choosing a winner.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:NoticeResult/efac:LotResult/efac:DecisionReason/efbc:DecisionReasonCode</span></code>
        </td>
        <td class="mapping">

<a href="operations.md#get-the-award-for-a-lotresult">Get the award for the LotResult</a> and set the award's `.status` to 'unsuccessful'.

Look up the code's label in the <a href="https://op.europa.eu/en/web/eu-vocabularies/concept-scheme/-/resource?uri=http://publications.europa.eu/resource/authority/non-award-justification">authority table</a> and map it to the award's `.statusDetails`.

```xml
<efac:DecisionReason>
  <efbc:DecisionReasonCode listName="non-award-justification">no-rece</efbc:DecisionReasonCode>
</efac:DecisionReason>
```

```json
{
  "awards": [
    {
      "status": "unsuccessful",
      "statusDetails": "No tenders, requests to participate or projects were received"
    }
  ]
}
```

</td>
      </tr>
      <tr id="BT-145-Contract">
        <td class="field break-all">
            <p><b>BT-145-Contract</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/competition-results.html#settledContractSection"></a><br>Contract Conclusion Date</p><p><i>BT-145:</i> The date when the contract was concluded. Typically, this is the date when the last contractual party signed the contract. However, if no contract is signed, then the date of contract conclusion may correspond to other dates (e.g. the date when the buyer notified the winning tenderer). The date of contract conclusion is always later than the end of the standstill period and the moment when any evidence submitted by the winner has been verified.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:NoticeResult/efac:SettledContract/cbc:IssueDate</span></code>
        </td>
        <td class="mapping">

<a href="operations.md#get-the-contract-for-a-settledcontract">Get the contract for the SettledContract</a>, <a href="operations.md#convert-a-date-to-iso-format">convert date to ISO format</a> and map to the contract's `.dateSigned`.

```xml
<efac:SettledContract>
  <cbc:IssueDate>2021-02-21+01:00</cbc:IssueDate>
</efac:SettledContract>
```

```json
{
  "contracts": [
    {
      "dateSigned": "2021-02-21T23:59:59+01:00"
    }
  ]
}
```

</td>
      </tr>
      <tr id="BT-1451-Contract">
        <td class="field break-all">
            <p><b>BT-1451-Contract</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/competition-results.html#settledContractSection"></a><br>Winner Decision Date</p><p><i>BT-1451:</i> The date of the official decision choosing the winning tender.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:NoticeResult/efac:SettledContract/cbc:AwardDate</span></code>
        </td>
        <td class="mapping">

For each `ancestor::efac:NoticeResult/efac:LotResult` with an `/efac:SettledContract/cbc:ID` equal to the value of `ancestor::efac:SettledContract/cbc:ID`:

- <a href="operations.md#get-the-award-for-a-lotresult">Get the award for the LotResult</a>.
- If the award's `.date` is not yet set or if the winner decision date is earlier than the award's `.date`, <a href="operations.md#convert-a-date-to-iso-format">convert date to ISO format</a> and map to the award's `.date`. Otherwise, discard.

```xml
<efac:SettledContract>
  <cbc:AwardDate>2021-02-19+01:00</cbc:AwardDate>
</efac:SettledContract>
```

```json
{
  "awards": [
    {
      "date": "2021-02-19T23:59:59+01:00"
    }
  ]
}
```

</td>
      </tr>
      <tr id="BT-15-Lot">
        <td class="field break-all">
            <p><b>BT-15-Lot</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/procedure-lot-part-information.html#procurementDocsSection"></a><br>Documents URL</p><p><i>BT-15:</i> The internet address for accessing (the non-restricted part of) the procurement documents. For all notices except prior information notices, the address shall give access that is direct (i.e. the exact webpage with the documents, not a general website), unrestricted (e.g. no registration), full (i.e. the procurement documents are complete) and free of charge and the documents shall be available already at the time of the publication of the notice.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='Lot']/cac:TenderingTerms/cac:CallForTendersDocumentReference[not(cbc:DocumentType/text()='restricted-document')]/cac:Attachment/cac:ExternalReference/cbc:URI</span></code>
        </td>
        <td class="mapping">

<a href="operations.md#get-the-document-for-a-document-reference">Get the document for the document reference</a>.

Map to the document's `.url` and set its `.documentType` to 'biddingDocuments'.

Add the value of `ancestor::cac:ProcurementProjectLot/cbc:ID` to `.relatedLots`.

```xml
<cac:ProcurementProjectLot>
  <cbc:ID schemeName="Lot">LOT-0001</cbc:ID>
  <cac:TenderingTerms>
    <cac:CallForTendersDocumentReference>
      <cbc:ID>20210521/CTFD/ENG/7654-02</cbc:ID>
      <cac:Attachment>
        <cac:ExternalReference>
          <cbc:URI>https://mywebsite.com/proc/2019024/accessinfo</cbc:URI>
        </cac:ExternalReference>
      </cac:Attachment>
    </cac:CallForTendersDocumentReference>
  </cac:TenderingTerms>
</cac:ProcurementProjectLot>
```

```json
{
  "tender": {
    "documents": [
      {
        "id": "20210521/CTFD/ENG/7654-02",
        "documentType": "biddingDocuments",
        "relatedLots": [
          "LOT-0001"
        ],
        "url": "https://mywebsite.com/proc/2019024/accessinfo"
      }
    ]
  }
}
```

</td>
      </tr>
      <tr id="BT-15-Part">
        <td class="field break-all">
            <p><b>BT-15-Part</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/procedure-lot-part-information.html#procurementDocsSection"></a><br>Documents URL</p><p><i>BT-15:</i> The internet address for accessing (the non-restricted part of) the procurement documents. For all notices except prior information notices, the address shall give access that is direct (i.e. the exact webpage with the documents, not a general website), unrestricted (e.g. no registration), full (i.e. the procurement documents are complete) and free of charge and the documents shall be available already at the time of the publication of the notice.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='Part']/cac:TenderingTerms/cac:CallForTendersDocumentReference[not(cbc:DocumentType/text()='restricted-document')]/cac:Attachment/cac:ExternalReference/cbc:URI</span></code>
        </td>
        <td class="mapping">

<a href="operations.md#get-the-document-for-a-document-reference">Get the document for the document reference</a>

Map to the document's `.url` and set its `.documentType` to 'biddingDocuments'

```xml
<cac:CallForTendersDocumentReference>
  <cbc:ID>20210521/CTFD/ENG/7654-02</cbc:ID>
  <cac:Attachment>
    <cac:ExternalReference>
      <cbc:URI>https://mywebsite.com/proc/2019024/accessinfo</cbc:URI>
    </cac:ExternalReference>
  </cac:Attachment>
</cac:CallForTendersDocumentReference>
```

```json
{
  "tender": {
    "documents": [
      {
        "id": "20210521/CTFD/ENG/7654-02",
        "documentType": "biddingDocuments",
        "url": "https://mywebsite.com/proc/2019024/accessinfo"
      }
    ]
  }
}
```

</td>
      </tr>
      <tr id="BT-150-Contract">
        <td class="field break-all">
            <p><b>BT-150-Contract</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/competition-results.html#settledContractSection"></a><br>Contract Identifier</p><p><i>BT-150:</i> An identifier of the contract or, in case of voluntary-ex ante transparency notices and design contest result notices, of the decision. The information in the contract section refers to this contract or decision.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:NoticeResult/efac:SettledContract/efac:ContractReference/cbc:ID</span></code>
        </td>
        <td class="mapping">

- <a href="operations.md#get-the-contract-for-a-settledcontract">Get the contract for the SettledContract</a>.
- Add a `SimpleIdentifier` to the contract's `.identifiers` array.
- If the scope of the list, register or scheme from which the contract identifier is drawn is subnational, set the simple identifier's `.scheme` to `{ISO 3166-1 alpha-2}-{system}`. Otherwise, set it to `{ISO 3166-2}-{system}`.
- Map to the simple identifier's `.id`.

```xml
<efac:SettledContract>
  <efac:ContractReference>
    <cbc:ID>CRN ABC:EFG/2020-01</cbc:ID>
  </efac:ContractReference>
</efac:SettledContract>
```

```json
{
  "contracts": [
    {
      "identifiers": [
        {
          "id": "CRN ABC:EFG/2020-01",
          "scheme": "NL-TENDERNED"
        }
      ]
    }
  ]
}
```

</td>
      </tr>
      <tr id="BT-1501(n)-Contract">
        <td class="field break-all">
            <p><b>BT-1501(n)-Contract</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/contract-modification-notice.html"></a><br>Modification Previous Notice Identifier</p><p><i>BT-1501:</i> An identifier of one or more sections within a previous notice within the procedure. The information in the modification section refers to this section or these sections.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:ContractModification/efbc:ChangedNoticeIdentifier</span></code>
        </td>
        <td class="mapping">

Discard. The notice and sections that were modified can be determined by comparing previous releases with the current release.

```xml
<efac:ContractModification>
  <efac:Change>
    <efbc:ChangedSectionIdentifier>LOT-0002</efbc:ChangedSectionIdentifier>
  </efac:Change>
</efac:ContractModification>
```



</td>
      </tr>
      <tr id="BT-1501(s)-Contract">
        <td class="field break-all">
            <p><b>BT-1501(s)-Contract</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/contract-modification-notice.html"></a><br>Modification Previous Notice Section Identifier</p><p><i>BT-1501:</i> An identifier of one or more sections within a previous notice within the procedure. The information in the modification section refers to this section or these sections.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:ContractModification/efac:Change/efbc:ChangedSectionIdentifier</span></code>
        </td>
        <td class="mapping">

Discard. The notice and sections that were modified can be determined by comparing previous releases with the current release.

```xml
<efac:ContractModification>
  <efac:Change>
    <efbc:ChangedSectionIdentifier>LOT-0002</efbc:ChangedSectionIdentifier>
  </efac:Change>
</efac:ContractModification>
```



</td>
      </tr>
      <tr id="BT-151-Contract">
        <td class="field break-all">
            <p><b>BT-151-Contract</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/competition-results.html#settledContractSection"></a><br>Contract URL</p><p><i>BT-151:</i> The uniform resource locator (e.g. the web address) of the contract.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:NoticeResult/efac:SettledContract/cbc:URI</span></code>
        </td>
        <td class="mapping">

- <a href="operations.md#get-the-contract-for-a-settledcontract">Get the contract for the SettledContract</a>.
- Add a `Document` to its `.documents` array, and:
  - Set its `.id` incrementally.
  - Set its `.documentType` to 'contractSigned'.
  - Map to its `.url`.

```xml
<efac:SettledContract>
  <cbc:URI>http://mycontract.acme.com/1234/</cbc:URI>
</efac:SettledContract>
```

```json
{
  "contracts": [
    {
      "documents": [
        {
          "url": "http://mycontract.acme.com/1234/",
          "documentType": "contractSigned"
        }
      ]
    }
  ]
}
```

</td>
      </tr>
      <tr id="BT-156-NoticeResult">
        <td class="field break-all">
            <p><b>BT-156-NoticeResult</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/competition-results.html#_notice_aggregated_amounts"></a><br>Group Framework Maximum Value</p><p><i>BT-156:</i> It is the re-calculated maximum value likely to be spent for a group of lots within the procedure. This information can be provided when the maximum value of a group of lots is lower than the sum of values of individual lots (e.g. when the same budget is shared for several lots). The value covers all contracts to be awarded within a framework agreement over its whole duration, including options and renewals. The value is re-calculated on the basis of the winner’s tender or winners’ tenders.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:NoticeResult/efac:GroupFramework/efbc:GroupFrameworkMaximumValueAmount</span></code>
        </td>
        <td class="mapping">

Discard.

```xml
<efac:NoticeResult>
  <efac:GroupFramework>
    <efbc:GroupFrameworkMaximumValueAmount currencyID="EUR">800000</efbc:GroupFrameworkMaximumValueAmount>
  </efac:GroupFramework>
</efac:NoticeResult>
```



</td>
      </tr>
      <tr id="BT-1561-NoticeResult">
        <td class="field break-all">
            <p><b>BT-1561-NoticeResult</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/competition-results.html#_notice_aggregated_amounts"></a><br>Group Framework Re-estimated Value</p><p><i>BT-1561:</i> The value likely to be spent, within a framework agreement, for a group of lots. This information can be provided when the value likely to be spent for a group of lots is lower than the sum of values likely to be spent for individual lots (e.g. when the same budget is shared for several lots). The value covers all contracts to be awarded within a framework agreement over its whole duration, including options and renewals. The re-estimated value is the value likely to be spent, as re-estimated on the basis of the winner’s tender or winners’ tenders.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:NoticeResult/efac:GroupFramework/efbc:GroupFrameworkReestimatedValueAmount</span></code>
        </td>
        <td class="mapping">

Discard.

```xml
<efac:NoticeResult>
  <efac:GroupFramework>
    <efbc:GroupFrameworkReestimatedValueAmount currencyID="EUR">800000</efbc:GroupFrameworkReestimatedValueAmount>
  </efac:GroupFramework>
</efac:NoticeResult>
```



</td>
      </tr>
      <tr id="BT-157-LotsGroup">
        <td class="field break-all">
            <p><b>BT-157-LotsGroup</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/procedure-lot-part-information.html#frameworkAgreementSection"></a><br>Group Framework Maximum Value</p><p><i>BT-157:</i> The maximum value which may be spent in a framework agreement within a group of lots. This information can be provided when the maximum value of a group of lots is lower than the sum of maximum values of individual lots in this group (e.g. when the same budget is shared for several lots).  Maximum value means a value covering all contracts to be awarded within a framework agreement over its whole duration, including options and renewals.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='LotsGroup']/cac:TenderingProcess/cac:FrameworkAgreement/cbc:EstimatedMaximumValueAmount</span></code>
        </td>
        <td class="mapping">

<a href="operations.md#get-the-lot-group-for-a-procurementprojectlot">Get the lot group for the ProcurementProjectLot</a>. Map to its `.techniques.frameworkAgreement.value.amount` and map `currencyID` to its `techniques.frameworkAgreement.value.currency`.

```xml
<cac:FrameworkAgreement>
  <cbc:EstimatedMaximumValueAmount currencyID="EUR">200000</cbc:EstimatedMaximumValueAmount>
</cac:FrameworkAgreement>
```

```json
{
  "tender": {
    "lotGroups": [
      {
        "techniques": {
          "frameworkAgreement": {
            "value": {
              "amount": 800000,
              "currency": "EUR"
            }
          }
        }
      }
    ]
  }
}
```

</td>
      </tr>
      <tr id="BT-16-Organization-Company">
        <td class="field break-all">
            <p><b>BT-16-Organization-Company</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/parties.html#_general_structure_of_an_organization_related_information"></a><br>Organisation Part Name</p><p><i>BT-16:</i> The name of a part of an organisation (e.g. the relevant department of a large buyer).</p>
            <code class="docutils literal notranslate"><span class="pre">/*/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:Organizations/efac:Organization/efac:Company/cac:PostalAddress/cbc:Department</span></code>
        </td>
        <td class="mapping">

<a href="operations.md#get-the-organization-for-a-company">Get the organization for the company</a> and append to the organization's `.name`, separated from the original text with ' - ' (space, dash, space).

See also <a href="https://standard.open-contracting.org/latest/en/guidance/map/organizational_units/#using-the-organization-building-block-with-an-organizational-hierarchy">Using the Organization building block with an organizational hierarchy</a>.

```xml
<efac:Organization>
  <efac:Company>
    <cac:PostalAddress>
      <cbc:Department>Procurement Department</cbc:Department>
    </cac:PostalAddress>
  </efac:Company>
</efac:Organization>
```

```json
{
  "parties": [
    {
      "name": "Ministry of Education - Procurement Department"
    }
  ]
}
```

</td>
      </tr>
      <tr id="BT-16-Organization-TouchPoint">
        <td class="field break-all">
            <p><b>BT-16-Organization-TouchPoint</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/parties.html#_general_structure_of_an_organization_related_information"></a><br>Part Name</p><p><i>BT-16:</i> The name of a part of an organisation (e.g. the relevant department of a large buyer).</p>
            <code class="docutils literal notranslate"><span class="pre">/*/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:Organizations/efac:Organization/efac:TouchPoint/cac:PostalAddress/cbc:Department</span></code>
        </td>
        <td class="mapping">

<a href="operations.md#get-the-organization-for-a-touchpoint">Get the organization the touchpoint</a> and append to the organization's `.name`, separated from the original text with ' - ' (space, dash, space).

See also <a href="https://standard.open-contracting.org/latest/en/guidance/map/organizational_units/#using-the-organization-building-block-with-an-organizational-hierarchy">Using the Organization building block with an organizational hierarchy</a>.

```xml
<efac:Organization>
  <efac:TouchPoint>
    <cac:PartyName>
      <cbc:Name languageID="ENG">Legal Department</cbc:Name>
    </cac:PartyName>
    <cac:PostalAddress>
      <cbc:Department>Department XYZ</cbc:Department>
    </cac:PostalAddress>
  </efac:TouchPoint>
</efac:Organization>
```

```json
{
  "parties": [
    {
      "name": "Ministry of Education - Legal Department"
    }
  ]
}
```

</td>
      </tr>
      <tr id="BT-160-Tender">
        <td class="field break-all">
            <p><b>BT-160-Tender</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/competition-results.html#lotTenderSection"></a><br>Concession Revenue Buyer</p><p><i>BT-160:</i> The estimated revenue coming from the buyer who granted the concession (e.g. prizes and payments).</p>
            <code class="docutils literal notranslate"><span class="pre">/*/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:NoticeResult/efac:LotTender/efac:ConcessionRevenue/efbc:RevenueBuyerAmount</span></code>
        </td>
        <td class="mapping">

Get the value of `ancestor::efac:SettledContract/cbc:ID` whose `efac:LotTender/cbc:ID` is equal to the value of `ancestor::efac:LotTender/cbc:ID` and <a href="operations.md#get-the-contract-for-a-settledcontract">get the contract for this SettledContract</a>.

Add a `Charge` object to the contract's `.implementation.charges` array.

- Set its `.id` to 'government'.
- Set its `.paidBy` to 'government'.
- Set its `.title` to the <a href="operations.md#get-a-translation">translation</a> of 'The estimated revenue coming from the buyer who granted the concession (e.g. prizes and payments).'.
- Map the value of this field to its `.estimatedValue.amount` and `@currencyID` to the estimatedValue's `.currency`.

```xml
<efac:ConcessionRevenue>
  <efbc:RevenueBuyerAmount currencyID="EUR">350</efbc:RevenueBuyerAmount>
</efac:ConcessionRevenue>
```

```json
{
  "contracts": [
    {
      "implementation": {
        "charges": [
          {
            "id": "government",
            "title": "The estimated revenue coming from the buyer who granted the concession (e.g. prizes and payments).",
            "estimatedValue": {
              "amount": 350,
              "currency": "EUR"
            },
            "paidBy": "government"
          }
        ]
      }
    }
  ]
}
```

</td>
      </tr>
      <tr id="BT-161-NoticeResult">
        <td class="field break-all">
            <p><b>BT-161-NoticeResult</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/competition-results.html#_notice_aggregated_amounts"></a><br>Notice Value</p><p><i>BT-161:</i> The value of all contracts awarded in this notice, including options and renewals.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:NoticeResult/cbc:TotalAmount</span></code>
        </td>
        <td class="mapping">

Discard. This is derived from the `value` of awards.

```xml
<efac:NoticeResult>
  <cbc:TotalAmount currencyID="EUR">123456.00</cbc:TotalAmount>
</efac:NoticeResult>
```



</td>
      </tr>
      <tr id="BT-162-Tender">
        <td class="field break-all">
            <p><b>BT-162-Tender</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/competition-results.html#lotTenderSection"></a><br>Concession Revenue User</p><p><i>BT-162:</i> The estimated revenue coming from the users of the concession (e.g. fees and fines).</p>
            <code class="docutils literal notranslate"><span class="pre">/*/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:NoticeResult/efac:LotTender/efac:ConcessionRevenue/efbc:RevenueUserAmount</span></code>
        </td>
        <td class="mapping">

Get the value of `ancestor::efac:SettledContract/cbc:ID` whose `efac:LotTender/cbc:ID` is equal to the value of `ancestor::efac:LotTender/cbc:ID` and <a href="operations.md#get-the-contract-for-a-settledcontract">get the contract for this SettledContract</a>.

Add a `Charge` object to the contract's `.implementation.charges` array.

- Set its `.id` to 'user'.
- Set its `.paidBy` to 'user'.
- Set its `.title` to the <a href="operations.md#get-a-translation">translation</a> of 'he estimated revenue coming from the users of the concession (e.g. fees and fines).'.
- Map to its `.estimatedValue.amount` and `@currencyID` to the estimatedValue's `.currency`.

```xml
<efac:ConcessionRevenue>
  <efbc:RevenueUserAmount currencyID="EUR">350</efbc:RevenueUserAmount>
</efac:ConcessionRevenue>
```

```json
{
  "contracts": [
    {
      "implementation": {
        "charges": [
          {
            "id": "user",
            "title": "he estimated revenue coming from the users of the concession (e.g. fees and fines).",
            "estimatedValue": {
              "amount": 350,
              "currency": "EUR"
            },
            "paidBy": "user"
          }
        ]
      }
    }
  ]
}
```

</td>
      </tr>
      <tr id="BT-163-Tender">
        <td class="field break-all">
            <p><b>BT-163-Tender</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/competition-results.html#lotTenderSection"></a><br>Concession Value Description</p><p><i>BT-163:</i> The description of the method used for calculating the estimated value of the concession and any other relevant information concerning the value of the concession.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:NoticeResult/efac:LotTender/efac:ConcessionRevenue/efbc:ValueDescription</span></code>
        </td>
        <td class="mapping">

Get the value of `ancestor::efac:LotResult/cbc:ID` whose `efac:LotTender/cbc:ID` is equal to the value of `ancestor::efac:LotTender/cbc:ID`.

Get the `Award` in `awards` whose `id` is equal to the value of this `efac:LotResult/cbc:ID`. If none exists yet:

- Add an `Award` to `awards`.
- Set its `.id` to the value of this `efac:LotResult/cbc:ID`.
- Add the value of `efac:LotResult/efac:TenderLot/cbc:ID` to its `.relatedLots`.

Map to the award's `.valueCalculationMethod`.

```xml
<efac:ConcessionRevenue>
  <efbc:ValueDescription>The awarded value takes into account the growing revenue expected from fees.</efbc:ValueDescription>
</efac:ConcessionRevenue>
```

```json
{
  "awards": [
    {
      "valueCalculationMethod": "The awarded value takes into account the growing revenue expected from fees."
    }
  ]
}
```

</td>
      </tr>
      <tr id="BT-165-Organization-Company">
        <td class="field break-all">
            <p><b>BT-165-Organization-Company</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/parties.html#_general_structure_of_an_organization_related_information"></a><br>Winner Size</p><p><i>BT-165:</i> The size of the winner, tenderer or subcontractor (e.g. micro enterprise, small enterprise, medium enterprise).</p>
            <code class="docutils literal notranslate"><span class="pre">/*/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:Organizations/efac:Organization/efac:Company[(cac:PartyIdentification/cbc:ID/text() = //efac:TenderingParty/efac:Tenderer/cbc:ID/text()) or (cac:PartyIdentification/cbc:ID/text() = //efac:TenderingParty/efac:Subcontractor/cbc:ID/text())]/efbc:CompanySizeCode</span></code>
        </td>
        <td class="mapping">

<a href="operations.md#get-the-organization-for-a-company">Get the organization for the company</a> and map to the organization's `.details.scale`

```xml
<efac:Company>
  <efbc:CompanySizeCode listName="economic-operator-size">large</efbc:CompanySizeCode>
</efac:Company>
```

```json
{
  "parties": [
    {
      "details": {
        "scale": "large"
      }
    }
  ]
}
```

</td>
      </tr>
      <tr id="BT-17-Lot">
        <td class="field break-all">
            <p><b>BT-17-Lot</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/procedure-lot-part-information.html#eSubmissionSection"></a><br>SubmissionElectronic</p><p><i>BT-17:</i> Whether economic operators are required, allowed, or not allowed to submit tenders, requests to participate, or expressions of interest electronically.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='Lot']/cac:TenderingProcess/cbc:SubmissionMethodCode[@listName='esubmission']</span></code>
        </td>
        <td class="mapping">

<a href="operations.md#get-the-lot-for-a-procurementprojectlot">Get the lot for the ProcurementProjectLot</a> and map to its `.submissionTerms.electronicSubmissionPolicy`.

If "allowed" or "required", add 'electronicSubmission' to the lot's `.submissionMethod` array.

```xml
<cbc:SubmissionMethodCode listName="esubmission">allowed</cbc:SubmissionMethodCode>
```

```json
{
  "tender": {
    "lots": [
      {
        "submissionMethod": "electronicSubmission",
        "submissionTerms": {
          "electronicSubmissionPolicy": "allowed"
        }
      }
    ]
  }
}
```

</td>
      </tr>
      <tr id="BT-171-Tender">
        <td class="field break-all">
            <p><b>BT-171-Tender</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/competition-results.html#lotTenderSection"></a><br>Tender Rank</p><p><i>BT-171:</i> The position of the tender (i.e. whether the tender ended up first, second, third, etc.) in a design contest, a framework agreement with multiple winners (e.g. cascades), an innovation partnership, a competitive dialogue, or another procedure.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:NoticeResult/efac:LotTender/cbc:RankCode</span></code>
        </td>
        <td class="mapping">

<a href="operations.md#get-the-bid-for-a-lottender">Get the bid for a LotTender</a> and map to the bid's `.rank`.

```xml
<efac:LotTender>
  <cbc:RankCode>1</cbc:RankCode>
</efac:LotTender>
```

```json
{
  "bids": {
    "details": [
      {
        "rank": 1
      }
    ]
  }
}
```

</td>
      </tr>
      <tr id="BT-1711-Tender">
        <td class="field break-all">
            <p><b>BT-1711-Tender</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/competition-results.html#lotTenderSection"></a><br>Tender Ranked</p><p><i>BT-1711:</i> The tender was ranked. (This is not the rank itself, but only whether the ranking took place).  </p>
            <code class="docutils literal notranslate"><span class="pre">/*/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:NoticeResult/efac:LotTender/efbc:TenderRankedIndicator</span></code>
        </td>
        <td class="mapping">

<a href="operations.md#get-the-bid-for-a-lottender">Get the bid for a LotTender</a> and map to the bid's `.hasRank`.

```xml
<efac:LotTender>
  <efbc:TenderRankedIndicator>true</efbc:TenderRankedIndicator>
</efac:LotTender>
```

```json
{
  "bids": {
    "details": [
      {
        "hasRank": true
      }
    ]
  }
}
```

</td>
      </tr>
      <tr id="BT-18-Lot">
        <td class="field break-all">
            <p><b>BT-18-Lot</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/procedure-lot-part-information.html#partiesSection"></a><br>Submission URL</p><p><i>BT-18:</i> The internet address for submission of tenders, requests to participate, or expressions of interest by electronic means. The address shall be as direct as possible (ideally a dedicated address for the electronic submission, not just a general website).</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='Lot']/cac:TenderingTerms/cac:TenderRecipientParty/cbc:EndpointID</span></code>
        </td>
        <td class="mapping">

<a href="operations.md#get-the-lot-for-a-procurementprojectlot">Get the lot for the ProcurementProjectLot</a> and map to its `.submissionMethodDetails`.

```xml
<cac:TenderRecipientParty>
  <cbc:EndpointID>https://www.acme.com/tender-submission/</cbc:EndpointID>
</cac:TenderRecipientParty>
```

```json
{
  "tender": {
    "lots": [
      {
        "submissionMethodDetails": "https://www.acme.com/tender-submission/"
      }
    ]
  }
}
```

</td>
      </tr>
      <tr id="BT-19-Lot">
        <td class="field break-all">
            <p><b>BT-19-Lot</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/procedure-lot-part-information.html#nonelectronicSection"></a><br>Submission Nonelectronic Justification</p><p><i>BT-19:</i> The justification for electronic submission of tenders, requests to participate, or expressions of interest not being possible.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='Lot']/cac:TenderingProcess/cac:ProcessJustification/cbc:ProcessReasonCode[@listName='no-esubmission-justification']</span></code>
        </td>
        <td class="mapping">

<a href="operations.md#get-the-lot-for-a-procurementprojectlot">Get the lot for the ProcurementProjectLot</a>. Look up the code's label in the <a href="https://op.europa.eu/en/web/eu-vocabularies/concept-scheme/-/resource?uri=http://publications.europa.eu/resource/authority/communication-justification">authority table</a> and map it to the lot's `.submissionTerms.nonElectronicRationale`.

```xml
<cac:ProcessJustification>
  <cbc:ProcessReasonCode listName="no-esubmission-justification">phy-mod</cbc:ProcessReasonCode>
</cac:ProcessJustification>
```

```json
{
  "tender": {
    "lots": [
      {
        "submissionTerms": {
          "nonElectronicRationale": "Inclusion of a physical model"
        }
      }
    ]
  }
}
```

</td>
      </tr>
      <tr id="BT-191-Tender">
        <td class="field break-all">
            <p><b>BT-191-Tender</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/competition-results.html#lotTenderSection"></a><br>Country Origin</p><p><i>BT-191:</i> A country of origin of the product or the service.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:NoticeResult/efac:LotTender/efac:Origin/efbc:AreaCode</span></code>
        </td>
        <td class="mapping">

1. <a href="operations.md#get-the-bid-for-a-lottender">Get the bid for a LotTender</a>.
2. If the value of the field is `1A0` (Kosovo), add 'XK' to the bid's `.countriesOfOrigin` array. Otherwise, look up the equivalent ISO 3166-1 alpha-2 code in the <a href="https://op.europa.eu/en/web/eu-vocabularies/concept-scheme/-/resource?uri=http://publications.europa.eu/resource/authority/country">authority table</a> and add to the bid's `.countriesOfOrigin` array.

```xml
<efac:Origin>
  <efbc:AreaCode listName="eforms-country">ITA</efbc:AreaCode>
</efac:Origin>
```

```json
{
  "bids": {
    "details": [
      {
        "countriesOfOrigin": [
          "IT"
        ]
      }
    ]
  }
}
```

</td>
      </tr>
      <tr id="BT-193-Tender">
        <td class="field break-all">
            <p><b>BT-193-Tender</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/competition-results.html#lotTenderSection"></a><br>Tender Variant</p><p><i>BT-193:</i> The tender is a variant.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:NoticeResult/efac:LotTender/efbc:TenderVariantIndicator</span></code>
        </td>
        <td class="mapping">

<a href="operations.md#get-the-bid-for-a-lottender">Get the bid for a LotTender</a> and set the bid's `.variant` to `true`.

```xml
<efac:LotTender>
  <efbc:TenderVariantIndicator>true</efbc:TenderVariantIndicator>
</efac:LotTender>
```

```json
{
  "bids": {
    "details": [
      {
        "variant": true
      }
    ]
  }
}
```

</td>
      </tr>
      <tr id="BT-195(BT-09)-Procedure">
        <td class="field break-all">
            <p><b>BT-195(BT-09)-Procedure</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/withheld-publication.html#procedureLevelSection"></a><br>Unpublished Identifier</p><p><i>BT-195:</i> Identifier of the field that shall not be immediately published. Only fields concerning the Result value and groups of fields concerning the Tender and Procedure Lot Result can be unpublished. In the case of the European Parliament and Council Directive 2014/25/EU, the award criteria, the procurement procedure, certain dates and in certain cases information about the nature and quantity of a service can be unpublished as well.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:TenderingTerms/cac:ProcurementLegislationDocumentReference[cbc:ID/text()='CrossBorderLaw']/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:FieldsPrivacy[efbc:FieldIdentifierCode/text()='cro-bor-law']/efbc:FieldIdentifierCode</span></code>
        </td>
        <td class="mapping">

- Add a `withheldInformationItem` to the `withheldInformation` array, and:
  - Set its `.id` to `[efbc:FieldIdentifierCode]-[/*/cbc:ContractFolderID]`.
  - Set its `.field` to "cro-bor-law".
  - Set its `.name` to "Cross Border Law".

```xml
<efac:FieldsPrivacy>
  <efbc:FieldIdentifierCode listName="non-publication-identifier">cro-bor-law</efbc:FieldIdentifierCode>
</efac:FieldsPrivacy>
```

```json
{
  "withheldInformation": [
    {
      "field": "cro-bor-law",
      "id": "cro-bor-law-18d27a53-0109-4f93-9231-6659d931bce0",
      "name": "Cross Border Law"
    }
  ]
}
```

</td>
      </tr>
      <tr id="BT-195(BT-105)-Procedure">
        <td class="field break-all">
            <p><b>BT-195(BT-105)-Procedure</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/withheld-publication.html#procedureLevelSection"></a><br>Unpublished Identifier</p><p><i>BT-195:</i> Identifier of the field that shall not be immediately published. Only fields concerning the Result value and groups of fields concerning the Tender and Procedure Lot Result can be unpublished. In the case of the European Parliament and Council Directive 2014/25/EU, the award criteria, the procurement procedure, certain dates and in certain cases information about the nature and quantity of a service can be unpublished as well.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:TenderingProcess/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:FieldsPrivacy[efbc:FieldIdentifierCode/text()='pro-typ']/efbc:FieldIdentifierCode</span></code>
        </td>
        <td class="mapping">

- Add a `withheldInformationItem` to the `withheldInformation` array, and:
  - Set its `.id` to `[efbc:FieldIdentifierCode]-[/*/cbc:ContractFolderID]`.
  - Set its `.field` to "pro-typ".
  - Set its `.name` to "Procedure Type".

```xml
<efac:FieldsPrivacy>
  <efbc:FieldIdentifierCode listName="non-publication-identifier">pro-typ</efbc:FieldIdentifierCode>
</efac:FieldsPrivacy>
```

```json
{
  "withheldInformation": [
    {
      "field": "pro-typ",
      "id": "pro-typ-18d27a53-0109-4f93-9231-6659d931bce0",
      "name": "Procedure Type"
    }
  ]
}
```

</td>
      </tr>
      <tr id="BT-195(BT-106)-Procedure">
        <td class="field break-all">
            <p><b>BT-195(BT-106)-Procedure</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/withheld-publication.html#procedureLevelSection"></a><br>Unpublished Identifier</p><p><i>BT-195:</i> Identifier of the field that shall not be immediately published. Only fields concerning the Result value and groups of fields concerning the Tender and Procedure Lot Result can be unpublished. In the case of the European Parliament and Council Directive 2014/25/EU, the award criteria, the procurement procedure, certain dates and in certain cases information about the nature and quantity of a service can be unpublished as well.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:TenderingProcess/cac:ProcessJustification[cbc:ProcessReasonCode/@listName='accelerated-procedure']/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:FieldsPrivacy[efbc:FieldIdentifierCode/text()='pro-acc']/efbc:FieldIdentifierCode</span></code>
        </td>
        <td class="mapping">

- Add a `withheldInformationItem` to the `withheldInformation` array, and:
  - Set its `.id` to `[efbc:FieldIdentifierCode]-[/*/cbc:ContractFolderID]`.
  - Set its `.field` to "pro-acc".
  - Set its `.name` to "Procedure Accelerated".

```xml
<efac:FieldsPrivacy>
  <efbc:FieldIdentifierCode listName="non-publication-identifier">pro-acc</efbc:FieldIdentifierCode>
</efac:FieldsPrivacy>
```

```json
{
  "withheldInformation": [
    {
      "field": "pro-acc",
      "id": "pro-acc-18d27a53-0109-4f93-9231-6659d931bce0",
      "name": "Procedure Accelerated"
    }
  ]
}
```

</td>
      </tr>
      <tr id="BT-195(BT-1118)-NoticeResult">
        <td class="field break-all">
            <p><b>BT-195(BT-1118)-NoticeResult</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/withheld-publication.html#_notice_result_level"></a><br>Unpublished Identifier</p><p><i>BT-195:</i> Identifier of the field that shall not be immediately published. Only fields concerning the Result value and groups of fields concerning the Tender and Procedure Lot Result can be unpublished. In the case of the European Parliament and Council Directive 2014/25/EU, the award criteria, the procurement procedure, certain dates and in certain cases information about the nature and quantity of a service can be unpublished as well.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:NoticeResult/efac:FieldsPrivacy[efbc:FieldIdentifierCode/text()='not-app-val']/efbc:FieldIdentifierCode</span></code>
        </td>
        <td class="mapping">

Discard

```xml
<efac:FieldsPrivacy>
  <efbc:FieldIdentifierCode listName="non-publication-identifier">pro-acc</efbc:FieldIdentifierCode>
</efac:FieldsPrivacy>
```



</td>
      </tr>
      <tr id="BT-195(BT-118)-NoticeResult">
        <td class="field break-all">
            <p><b>BT-195(BT-118)-NoticeResult</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/withheld-publication.html#_notice_result_level"></a><br>Unpublished Identifier</p><p><i>BT-195:</i> Identifier of the field that shall not be immediately published. Only fields concerning the Result value and groups of fields concerning the Tender and Procedure Lot Result can be unpublished. In the case of the European Parliament and Council Directive 2014/25/EU, the award criteria, the procurement procedure, certain dates and in certain cases information about the nature and quantity of a service can be unpublished as well.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:NoticeResult/efac:FieldsPrivacy[efbc:FieldIdentifierCode/text()='not-max-val']/efbc:FieldIdentifierCode</span></code>
        </td>
        <td class="mapping">

Discard.

```xml
<efac:FieldsPrivacy>
  <efbc:FieldIdentifierCode listName="non-publication-identifier">not-max-val</efbc:FieldIdentifierCode>
</efac:FieldsPrivacy>
```



</td>
      </tr>
      <tr id="BT-195(BT-1252)-Procedure">
        <td class="field break-all">
            <p><b>BT-195(BT-1252)-Procedure</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/withheld-publication.html#procedureLevelSection"></a><br>Unpublished Identifier</p><p><i>BT-195:</i> Identifier of the field that shall not be immediately published. Only fields concerning the Result value and groups of fields concerning the Tender and Procedure Lot Result can be unpublished. In the case of the European Parliament and Council Directive 2014/25/EU, the award criteria, the procurement procedure, certain dates and in certain cases information about the nature and quantity of a service can be unpublished as well.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:TenderingProcess/cac:ProcessJustification[cbc:ProcessReasonCode/@listName='direct-award-justification']/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:FieldsPrivacy[efbc:FieldIdentifierCode/text()='dir-awa-pre']/efbc:FieldIdentifierCode</span></code>
        </td>
        <td class="mapping">

- Add a `withheldInformationItem` to the `withheldInformation` array, and:
  - Set its `.id` to `[efbc:FieldIdentifierCode]-[/*/cbc:ContractFolderID]`.
  - Set its `.field` to "dir-awa-pre".
  - Set its `.name` to "Direct Award Justification Previous Procedure Identifier".

```xml
<efac:FieldsPrivacy>
  <efbc:FieldIdentifierCode listName="non-publication-identifier">dir-awa-pre</efbc:FieldIdentifierCode>
</efac:FieldsPrivacy>
```

```json
{
  "withheldInformation": [
    {
      "field": "dir-awa-pre",
      "id": "dir-awa-pre-18d27a53-0109-4f93-9231-6659d931bce0",
      "name": "Direct Award Justification Previous Procedure Identifier"
    }
  ]
}
```

</td>
      </tr>
      <tr id="BT-195(BT-135)-Procedure">
        <td class="field break-all">
            <p><b>BT-195(BT-135)-Procedure</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/withheld-publication.html#procedureLevelSection"></a><br>Unpublished Identifier</p><p><i>BT-195:</i> Identifier of the field that shall not be immediately published. Only fields concerning the Result value and groups of fields concerning the Tender and Procedure Lot Result can be unpublished. In the case of the European Parliament and Council Directive 2014/25/EU, the award criteria, the procurement procedure, certain dates and in certain cases information about the nature and quantity of a service can be unpublished as well.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:TenderingProcess/cac:ProcessJustification[cbc:ProcessReasonCode/@listName='direct-award-justification']/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:FieldsPrivacy[efbc:FieldIdentifierCode/text()='dir-awa-tex']/efbc:FieldIdentifierCode</span></code>
        </td>
        <td class="mapping">

- Add a `withheldInformationItem` to the `withheldInformation` array, and:
  - Set its `.id` to `[efbc:FieldIdentifierCode]-[/*/cbc:ContractFolderID]`.
  - Set its `.field` to "dir-awa-tex".
  - Set its `.name` to "Direct Award Justification".

```xml
<efac:FieldsPrivacy>
  <efbc:FieldIdentifierCode listName="non-publication-identifier">dir-awa-tex</efbc:FieldIdentifierCode>
</efac:FieldsPrivacy>
```

```json
{
  "withheldInformation": [
    {
      "field": "dir-awa-tex",
      "id": "dir-awa-tex-18d27a53-0109-4f93-9231-6659d931bce0",
      "name": "Direct Award Justification"
    }
  ]
}
```

</td>
      </tr>
      <tr id="BT-195(BT-1351)-Procedure">
        <td class="field break-all">
            <p><b>BT-195(BT-1351)-Procedure</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/withheld-publication.html#procedureLevelSection"></a><br>Unpublished Identifier</p><p><i>BT-195:</i> Identifier of the field that shall not be immediately published. Only fields concerning the Result value and groups of fields concerning the Tender and Procedure Lot Result can be unpublished. In the case of the European Parliament and Council Directive 2014/25/EU, the award criteria, the procurement procedure, certain dates and in certain cases information about the nature and quantity of a service can be unpublished as well.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:TenderingProcess/cac:ProcessJustification[cbc:ProcessReasonCode/@listName='accelerated-procedure']/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:FieldsPrivacy[efbc:FieldIdentifierCode/text()='pro-acc-jus']/efbc:FieldIdentifierCode</span></code>
        </td>
        <td class="mapping">

- Add a `withheldInformationItem` to the `withheldInformation` array, and:
  - Set its `.id` to `[efbc:FieldIdentifierCode]-[/*/cbc:ContractFolderID]`.
  - Set its `.field` to "pro-acc-jus".
  - Set its `.name` to "Procedure Accelerated Justification".

```xml
<efac:FieldsPrivacy>
  <efbc:FieldIdentifierCode listName="non-publication-identifier">pro-acc-jus</efbc:FieldIdentifierCode>
</efac:FieldsPrivacy>
```

```json
{
  "withheldInformation": [
    {
      "field": "pro-acc-jus",
      "id": "pro-acc-jus-18d27a53-0109-4f93-9231-6659d931bce0",
      "name": "Procedure Accelerated Justification"
    }
  ]
}
```

</td>
      </tr>
      <tr id="BT-195(BT-136)-Procedure">
        <td class="field break-all">
            <p><b>BT-195(BT-136)-Procedure</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/withheld-publication.html#procedureLevelSection"></a><br>Unpublished Identifier</p><p><i>BT-195:</i> Identifier of the field that shall not be immediately published. Only fields concerning the Result value and groups of fields concerning the Tender and Procedure Lot Result can be unpublished. In the case of the European Parliament and Council Directive 2014/25/EU, the award criteria, the procurement procedure, certain dates and in certain cases information about the nature and quantity of a service can be unpublished as well.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:TenderingProcess/cac:ProcessJustification[cbc:ProcessReasonCode/@listName='direct-award-justification']/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:FieldsPrivacy[efbc:FieldIdentifierCode/text()='dir-awa-jus']/efbc:FieldIdentifierCode</span></code>
        </td>
        <td class="mapping">

- Add a `withheldInformationItem` to the `withheldInformation` array, and:
  - Set its `.id` to `[efbc:FieldIdentifierCode]-[/*/cbc:ContractFolderID]`.
  - Set its `.field` to "dir-awa-jus".
  - Set its `.name` to "Direct Award Justification".

```xml
<efac:FieldsPrivacy>
  <efbc:FieldIdentifierCode listName="non-publication-identifier">dir-awa-jus</efbc:FieldIdentifierCode>
</efac:FieldsPrivacy>
```

```json
{
  "withheldInformation": [
    {
      "field": "dir-awa-jus",
      "id": "dir-awa-jus-18d27a53-0109-4f93-9231-6659d931bce0",
      "name": "Direct Award Justification"
    }
  ]
}
```

</td>
      </tr>
      <tr id="BT-195(BT-142)-LotResult">
        <td class="field break-all">
            <p><b>BT-195(BT-142)-LotResult</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/withheld-publication.html#lotResultLevelSection"></a><br>Unpublished Identifier</p><p><i>BT-195:</i> Identifier of the field that shall not be immediately published. Only fields concerning the Result value and groups of fields concerning the Tender and Procedure Lot Result can be unpublished. In the case of the European Parliament and Council Directive 2014/25/EU, the award criteria, the procurement procedure, certain dates and in certain cases information about the nature and quantity of a service can be unpublished as well.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:NoticeResult/efac:LotResult/efac:FieldsPrivacy[efbc:FieldIdentifierCode/text()='win-cho']/efbc:FieldIdentifierCode</span></code>
        </td>
        <td class="mapping">

- Add a `withheldInformationItem` to the `withheldInformation` array, and:
  - Set its `.id` to `[efbc:FieldIdentifierCode]-[ancestor::efac:LotResult/cbc:ID]`.
  - Set its `.field` to "win-cho".
  - Set its `.name` to "Winner Chosen".

```xml
<efac:FieldsPrivacy>
  <efbc:FieldIdentifierCode listName="non-publication-identifier">win-cho</efbc:FieldIdentifierCode>
</efac:FieldsPrivacy>
```

```json
{
  "withheldInformation": [
    {
      "field": "win-cho",
      "id": "win-cho-RES-0001",
      "name": "Winner Chosen"
    }
  ]
}
```

</td>
      </tr>
      <tr id="BT-195(BT-144)-LotResult">
        <td class="field break-all">
            <p><b>BT-195(BT-144)-LotResult</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/withheld-publication.html#lotResultLevelSection"></a><br>Unpublished Identifier</p><p><i>BT-195:</i> Identifier of the field that shall not be immediately published. Only fields concerning the Result value and groups of fields concerning the Tender and Procedure Lot Result can be unpublished. In the case of the European Parliament and Council Directive 2014/25/EU, the award criteria, the procurement procedure, certain dates and in certain cases information about the nature and quantity of a service can be unpublished as well.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:NoticeResult/efac:LotResult/efac:DecisionReason/efac:FieldsPrivacy[efbc:FieldIdentifierCode/text()='no-awa-rea']/efbc:FieldIdentifierCode</span></code>
        </td>
        <td class="mapping">

- Add a `withheldInformationItem` to the `withheldInformation` array, and:
  - Set its `.id` to `[efbc:FieldIdentifierCode]-[ancestor::efac:LotResult/cbc:ID]`.
  - Set its `.field` to "no-awa-rea".
  - Set its `.name` to "Not Awarded Reason".

```xml
<efac:FieldsPrivacy>
  <efbc:FieldIdentifierCode listName="non-publication-identifier">no-awa-rea</efbc:FieldIdentifierCode>
</efac:FieldsPrivacy>
```

```json
{
  "withheldInformation": [
    {
      "field": "no-awa-rea",
      "id": "no-awa-rea-RES-0001",
      "name": "Not Awarded Reason"
    }
  ]
}
```

</td>
      </tr>
      <tr id="BT-195(BT-156)-NoticeResult">
        <td class="field break-all">
            <p><b>BT-195(BT-156)-NoticeResult</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/withheld-publication.html#_notice_result_level"></a><br>Unpublished Identifier</p><p><i>BT-195:</i> Identifier of the field that shall not be immediately published. Only fields concerning the Result value and groups of fields concerning the Tender and Procedure Lot Result can be unpublished. In the case of the European Parliament and Council Directive 2014/25/EU, the award criteria, the procurement procedure, certain dates and in certain cases information about the nature and quantity of a service can be unpublished as well.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:NoticeResult/efac:GroupFramework/efac:FieldsPrivacy[efbc:FieldIdentifierCode/text()='gro-max-val']/efbc:FieldIdentifierCode</span></code>
        </td>
        <td class="mapping">

Discard.

```xml
<efac:FieldsPrivacy>
  <efbc:FieldIdentifierCode listName="non-publication-identifier">gro-max-val</efbc:FieldIdentifierCode>
</efac:FieldsPrivacy>
```



</td>
      </tr>
      <tr id="BT-195(BT-1561)-NoticeResult">
        <td class="field break-all">
            <p><b>BT-195(BT-1561)-NoticeResult</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/withheld-publication.html#_notice_result_level"></a><br>Unpublished Identifier</p><p><i>BT-195:</i> Identifier of the field that shall not be immediately published. Only fields concerning the Result value and groups of fields concerning the Tender and Procedure Lot Result can be unpublished. In the case of the European Parliament and Council Directive 2014/25/EU, the award criteria, the procurement procedure, certain dates and in certain cases information about the nature and quantity of a service can be unpublished as well.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:NoticeResult/efac:GroupFramework/efac:FieldsPrivacy[efbc:FieldIdentifierCode/text()='not-ree-val']/efbc:FieldIdentifierCode</span></code>
        </td>
        <td class="mapping">

Discard.

```xml
<efac:FieldsPrivacy>
  <efbc:FieldIdentifierCode listName="non-publication-identifier">gro-max-val</efbc:FieldIdentifierCode>
</efac:FieldsPrivacy>
```



</td>
      </tr>
      <tr id="BT-195(BT-160)-Tender">
        <td class="field break-all">
            <p><b>BT-195(BT-160)-Tender</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/withheld-publication.html#lotTenderLevelSection"></a><br>Unpublished Identifier</p><p><i>BT-195:</i> Identifier of the field that shall not be immediately published. Only fields concerning the Result value and groups of fields concerning the Tender and Procedure Lot Result can be unpublished. In the case of the European Parliament and Council Directive 2014/25/EU, the award criteria, the procurement procedure, certain dates and in certain cases information about the nature and quantity of a service can be unpublished as well.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:NoticeResult/efac:LotTender/efac:ConcessionRevenue/efac:FieldsPrivacy[efbc:FieldIdentifierCode/text()='con-rev-buy']/efbc:FieldIdentifierCode</span></code>
        </td>
        <td class="mapping">

- Add a `withheldInformationItem` to the `withheldInformation` array, and:
  - Set its `.id` to `[efbc:FieldIdentifierCode]-[ancestor::efac:LotTender/cbc:ID]`.
  - Set its `.field` to "con-rev-buy".
  - Set its `.name` to "Concession Revenue Buyer".

```xml
<efac:FieldsPrivacy>
  <efbc:FieldIdentifierCode listName="non-publication-identifier">con-rev-buy</efbc:FieldIdentifierCode>
</efac:FieldsPrivacy>
```

```json
{
  "withheldInformation": [
    {
      "field": "con-rev-buy",
      "id": "con-rev-buy-TEN-0001",
      "name": "Concession Revenue Buyer"
    }
  ]
}
```

</td>
      </tr>
      <tr id="BT-195(BT-161)-NoticeResult">
        <td class="field break-all">
            <p><b>BT-195(BT-161)-NoticeResult</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/withheld-publication.html#_notice_result_level"></a><br>Unpublished Identifier</p><p><i>BT-195:</i> Identifier of the field that shall not be immediately published. Only fields concerning the Result value and groups of fields concerning the Tender and Procedure Lot Result can be unpublished. In the case of the European Parliament and Council Directive 2014/25/EU, the award criteria, the procurement procedure, certain dates and in certain cases information about the nature and quantity of a service can be unpublished as well.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:NoticeResult/efac:FieldsPrivacy[efbc:FieldIdentifierCode/text()='not-val']/efbc:FieldIdentifierCode</span></code>
        </td>
        <td class="mapping">

Discard.

```xml
<efac:FieldsPrivacy>
  <efbc:FieldIdentifierCode listName="non-publication-identifier">not-val</efbc:FieldIdentifierCode>
</efac:FieldsPrivacy>
```



</td>
      </tr>
      <tr id="BT-195(BT-162)-Tender">
        <td class="field break-all">
            <p><b>BT-195(BT-162)-Tender</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/withheld-publication.html#lotTenderLevelSection"></a><br>Unpublished Identifier</p><p><i>BT-195:</i> Identifier of the field that shall not be immediately published. Only fields concerning the Result value and groups of fields concerning the Tender and Procedure Lot Result can be unpublished. In the case of the European Parliament and Council Directive 2014/25/EU, the award criteria, the procurement procedure, certain dates and in certain cases information about the nature and quantity of a service can be unpublished as well.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:NoticeResult/efac:LotTender/efac:ConcessionRevenue/efac:FieldsPrivacy[efbc:FieldIdentifierCode/text()='con-rev-use']/efbc:FieldIdentifierCode</span></code>
        </td>
        <td class="mapping">

- Add a `withheldInformationItem` to the `withheldInformation` array, and:
  - Set its `.id` to `[efbc:FieldIdentifierCode]-[ancestor::efac:LotTender/cbc:ID]`.
  - Set its `.field` to "con-rev-use".
  - Set its `.name` to "Concession Revenue User".

```xml
<efac:FieldsPrivacy>
  <efbc:FieldIdentifierCode listName="non-publication-identifier">con-rev-use</efbc:FieldIdentifierCode>
</efac:FieldsPrivacy>
```

```json
{
  "withheldInformation": [
    {
      "field": "con-rev-use",
      "id": "con-rev-use-TEN-0001",
      "name": "Concession Revenue User"
    }
  ]
}
```

</td>
      </tr>
      <tr id="BT-195(BT-163)-Tender">
        <td class="field break-all">
            <p><b>BT-195(BT-163)-Tender</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/withheld-publication.html#lotTenderLevelSection"></a><br>Unpublished Identifier</p><p><i>BT-195:</i> Identifier of the field that shall not be immediately published. Only fields concerning the Result value and groups of fields concerning the Tender and Procedure Lot Result can be unpublished. In the case of the European Parliament and Council Directive 2014/25/EU, the award criteria, the procurement procedure, certain dates and in certain cases information about the nature and quantity of a service can be unpublished as well.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:NoticeResult/efac:LotTender/efac:ConcessionRevenue/efac:FieldsPrivacy[efbc:FieldIdentifierCode/text()='val-con-des']/efbc:FieldIdentifierCode</span></code>
        </td>
        <td class="mapping">

- Add a `withheldInformationItem` to the `withheldInformation` array, and:
  - Set its `.id` to `[efbc:FieldIdentifierCode]-[ancestor::efac:LotTender/cbc:ID]`.
  - Set its `.field` to "val-con-des".
  - Set its `.name` to "Concession Value Description".

```xml
<efac:FieldsPrivacy>
  <efbc:FieldIdentifierCode listName="non-publication-identifier">val-con-des</efbc:FieldIdentifierCode>
</efac:FieldsPrivacy>
```

```json
{
  "withheldInformation": [
    {
      "field": "val-con-des",
      "id": "val-con-des-TEN-0001",
      "name": "Concession Value Description"
    }
  ]
}
```

</td>
      </tr>
      <tr id="BT-195(BT-171)-Tender">
        <td class="field break-all">
            <p><b>BT-195(BT-171)-Tender</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/withheld-publication.html#lotTenderLevelSection"></a><br>Unpublished Identifier</p><p><i>BT-195:</i> Identifier of the field that shall not be immediately published. Only fields concerning the Result value and groups of fields concerning the Tender and Procedure Lot Result can be unpublished. In the case of the European Parliament and Council Directive 2014/25/EU, the award criteria, the procurement procedure, certain dates and in certain cases information about the nature and quantity of a service can be unpublished as well.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:NoticeResult/efac:LotTender/efac:FieldsPrivacy[efbc:FieldIdentifierCode/text()='ten-ran']/efbc:FieldIdentifierCode</span></code>
        </td>
        <td class="mapping">

- Add a `withheldInformationItem` to the `withheldInformation` array, and:
  - Set its `.id` to `[efbc:FieldIdentifierCode]-[ancestor::efac:LotTender/cbc:ID]`.
  - Set its `.field` to "ten-ran".
  - Set its `.name` to "Tender Rank".

```xml
<efac:FieldsPrivacy>
  <efbc:FieldIdentifierCode listName="non-publication-identifier">ten-ran</efbc:FieldIdentifierCode>
</efac:FieldsPrivacy>
```

```json
{
  "withheldInformation": [
    {
      "field": "ten-ran",
      "id": "ten-ran-TEN-0001",
      "name": "Tender Rank"
    }
  ]
}
```

</td>
      </tr>
      <tr id="BT-195(BT-191)-Tender">
        <td class="field break-all">
            <p><b>BT-195(BT-191)-Tender</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/withheld-publication.html#lotTenderLevelSection"></a><br>Unpublished Identifier</p><p><i>BT-195:</i> Identifier of the field that shall not be immediately published. Only fields concerning the Result value and groups of fields concerning the Tender and Procedure Lot Result can be unpublished. In the case of the European Parliament and Council Directive 2014/25/EU, the award criteria, the procurement procedure, certain dates and in certain cases information about the nature and quantity of a service can be unpublished as well.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:NoticeResult/efac:LotTender/efac:Origin/efac:FieldsPrivacy[efbc:FieldIdentifierCode/text()='cou-ori']/efbc:FieldIdentifierCode</span></code>
        </td>
        <td class="mapping">

- Add a `withheldInformationItem` to the `withheldInformation` array, and:
  - Set its `.id` to `[efbc:FieldIdentifierCode]-[ancestor::efac:LotTender/cbc:ID]`.
  - Set its `.field` to "cou-ori".
  - Set its `.name` to "Country Origin".

```xml
<efac:FieldsPrivacy>
  <efbc:FieldIdentifierCode listName="non-publication-identifier">cou-ori</efbc:FieldIdentifierCode>
</efac:FieldsPrivacy>
```

```json
{
  "withheldInformation": [
    {
      "field": "cou-ori",
      "id": "cou-ori-TEN-0001",
      "name": "Country Origin"
    }
  ]
}
```

</td>
      </tr>
      <tr id="BT-195(BT-193)-Tender">
        <td class="field break-all">
            <p><b>BT-195(BT-193)-Tender</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/withheld-publication.html#lotTenderLevelSection"></a><br>Unpublished Identifier</p><p><i>BT-195:</i> Identifier of the field that shall not be immediately published. Only fields concerning the Result value and groups of fields concerning the Tender and Procedure Lot Result can be unpublished. In the case of the European Parliament and Council Directive 2014/25/EU, the award criteria, the procurement procedure, certain dates and in certain cases information about the nature and quantity of a service can be unpublished as well.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:NoticeResult/efac:LotTender/efac:FieldsPrivacy[efbc:FieldIdentifierCode/text()='win-ten-var']/efbc:FieldIdentifierCode</span></code>
        </td>
        <td class="mapping">

- Add a `withheldInformationItem` to the `withheldInformation` array, and:
  - Set its `.id` to `[efbc:FieldIdentifierCode]-[ancestor::efac:LotTender/cbc:ID]`.
  - Set its `.field` to "win-ten-var".
  - Set its `.name` to "Winning Tender Variant".

```xml
<efac:FieldsPrivacy>
  <efbc:FieldIdentifierCode listName="non-publication-identifier">win-ten-var</efbc:FieldIdentifierCode>
</efac:FieldsPrivacy>
```

```json
{
  "withheldInformation": [
    {
      "field": "win-ten-var",
      "id": "win-ten-var-TEN-0001",
      "name": "Winning Tender Variant"
    }
  ]
}
```

</td>
      </tr>
      <tr id="BT-195(BT-539)-Lot">
        <td class="field break-all">
            <p><b>BT-195(BT-539)-Lot</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/withheld-publication.html#lotsGroupOfLotsLevelSection"></a><br>Unpublished Identifier</p><p><i>BT-195:</i> Identifier of the field that shall not be immediately published. Only fields concerning the Result value and groups of fields concerning the Tender and Procedure Lot Result can be unpublished. In the case of the European Parliament and Council Directive 2014/25/EU, the award criteria, the procurement procedure, certain dates and in certain cases information about the nature and quantity of a service can be unpublished as well.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='Lot']/cac:TenderingTerms/cac:AwardingTerms/cac:AwardingCriterion/cac:SubordinateAwardingCriterion/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:FieldsPrivacy[efbc:FieldIdentifierCode/text()='awa-cri-typ']/efbc:FieldIdentifierCode</span></code>
        </td>
        <td class="mapping">

- Add a `withheldInformationItem` to the `withheldInformation` array, and:
  - Set its `.id` to `[efbc:FieldIdentifierCode]-[ancestor::cac:ProcurementProjectLot/cbc:ID schemeName="Lot"]`.
  - Set its `.field` to "awa-cri-typ".
  - Set its `.name` to "Award Criterion Type".

```xml
<efac:FieldsPrivacy>
  <efbc:FieldIdentifierCode listName="non-publication-identifier">awa-cri-typ</efbc:FieldIdentifierCode>
</efac:FieldsPrivacy>
```

```json
{
  "withheldInformation": [
    {
      "field": "awa-cri-typ",
      "id": "awa-cri-typ-LOT-0001",
      "name": "Award Criterion Type"
    }
  ]
}
```

</td>
      </tr>
      <tr id="BT-195(BT-539)-LotsGroup">
        <td class="field break-all">
            <p><b>BT-195(BT-539)-LotsGroup</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/withheld-publication.html#lotsGroupOfLotsLevelSection"></a><br>Unpublished Identifier</p><p><i>BT-195:</i> Identifier of the field that shall not be immediately published. Only fields concerning the Result value and groups of fields concerning the Tender and Procedure Lot Result can be unpublished. In the case of the European Parliament and Council Directive 2014/25/EU, the award criteria, the procurement procedure, certain dates and in certain cases information about the nature and quantity of a service can be unpublished as well.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='LotsGroup']/cac:TenderingTerms/cac:AwardingTerms/cac:AwardingCriterion/cac:SubordinateAwardingCriterion/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:FieldsPrivacy[efbc:FieldIdentifierCode/text()='awa-cri-typ']/efbc:FieldIdentifierCode</span></code>
        </td>
        <td class="mapping">

- Add a `withheldInformationItem` to the `withheldInformation` array, and:
  - Set its `.id` to `[efbc:FieldIdentifierCode]-[ancestor::cac:ProcurementProjectLot/cbc:ID schemeName="LotsGroup"]`.
  - Set its `.field` to "awa-cri-typ".
  - Set its `.name` to "Award Criterion Type".

```xml
<efac:FieldsPrivacy>
  <efbc:FieldIdentifierCode listName="non-publication-identifier">awa-cri-typ</efbc:FieldIdentifierCode>
</efac:FieldsPrivacy>
```

```json
{
  "withheldInformation": [
    {
      "field": "awa-cri-typ",
      "id": "awa-cri-typ-GLO-0001",
      "name": "Award Criterion Type"
    }
  ]
}
```

</td>
      </tr>
      <tr id="BT-195(BT-540)-Lot">
        <td class="field break-all">
            <p><b>BT-195(BT-540)-Lot</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/withheld-publication.html#lotsGroupOfLotsLevelSection"></a><br>Unpublished Identifier</p><p><i>BT-195:</i> Identifier of the field that shall not be immediately published. Only fields concerning the Result value and groups of fields concerning the Tender and Procedure Lot Result can be unpublished. In the case of the European Parliament and Council Directive 2014/25/EU, the award criteria, the procurement procedure, certain dates and in certain cases information about the nature and quantity of a service can be unpublished as well.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='Lot']/cac:TenderingTerms/cac:AwardingTerms/cac:AwardingCriterion/cac:SubordinateAwardingCriterion/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:FieldsPrivacy[efbc:FieldIdentifierCode/text()='awa-cri-des']/efbc:FieldIdentifierCode</span></code>
        </td>
        <td class="mapping">

- Add a `withheldInformationItem` to the `withheldInformation` array, and:
  - Set its `.id` to `[efbc:FieldIdentifierCode]-[ancestor::cac:ProcurementProjectLot/cbc:ID schemeName="Lot"]`.
  - Set its `.field` to "awa-cri-des".
  - Set its `.name` to "Award Criterion Description".

```xml
<efac:FieldsPrivacy>
  <efbc:FieldIdentifierCode listName="non-publication-identifier">awa-cri-des</efbc:FieldIdentifierCode>
</efac:FieldsPrivacy>
```

```json
{
  "withheldInformation": [
    {
      "field": "awa-cri-des",
      "id": "awa-cri-des-LOT-0001",
      "name": "Award Criterion Description"
    }
  ]
}
```

</td>
      </tr>
      <tr id="BT-195(BT-540)-LotsGroup">
        <td class="field break-all">
            <p><b>BT-195(BT-540)-LotsGroup</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/withheld-publication.html#lotsGroupOfLotsLevelSection"></a><br>Unpublished Identifier</p><p><i>BT-195:</i> Identifier of the field that shall not be immediately published. Only fields concerning the Result value and groups of fields concerning the Tender and Procedure Lot Result can be unpublished. In the case of the European Parliament and Council Directive 2014/25/EU, the award criteria, the procurement procedure, certain dates and in certain cases information about the nature and quantity of a service can be unpublished as well.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='LotsGroup']/cac:TenderingTerms/cac:AwardingTerms/cac:AwardingCriterion/cac:SubordinateAwardingCriterion/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:FieldsPrivacy[efbc:FieldIdentifierCode/text()='awa-cri-des']/efbc:FieldIdentifierCode</span></code>
        </td>
        <td class="mapping">

- Add a `withheldInformationItem` to the `withheldInformation` array, and:
  - Set its `.id` to `[efbc:FieldIdentifierCode]-[ancestor::cac:ProcurementProjectLot/cbc:ID schemeName="LotsGroup"]`.
  - Set its `.field` to "awa-cri-des".
  - Set its `.name` to "Award Criterion Description".

```xml
<efac:FieldsPrivacy>
  <efbc:FieldIdentifierCode listName="non-publication-identifier">awa-cri-des</efbc:FieldIdentifierCode>
</efac:FieldsPrivacy>
```

```json
{
  "withheldInformation": [
    {
      "field": "awa-cri-des",
      "id": "awa-cri-des-GLO-0001",
      "name": "Award Criterion Description"
    }
  ]
}
```

</td>
      </tr>
      <tr id="BT-195(BT-541)-Lot">
        <td class="field break-all">
            <p><b>BT-195(BT-541)-Lot</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/withheld-publication.html#lotsGroupOfLotsLevelSection"></a><br>Unpublished Identifier</p><p><i>BT-195:</i> Identifier of the field that shall not be immediately published. Only fields concerning the Result value and groups of fields concerning the Tender and Procedure Lot Result can be unpublished. In the case of the European Parliament and Council Directive 2014/25/EU, the award criteria, the procurement procedure, certain dates and in certain cases information about the nature and quantity of a service can be unpublished as well.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='Lot']/cac:TenderingTerms/cac:AwardingTerms/cac:AwardingCriterion/cac:SubordinateAwardingCriterion/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:AwardCriterionParameter/efac:FieldsPrivacy[efbc:FieldIdentifierCode/text()='awa-cri-num']/efbc:FieldIdentifierCode</span></code>
        </td>
        <td class="mapping">

- Add a `withheldInformationItem` to the `withheldInformation` array, and:
  - Set its `.id` to `[efbc:FieldIdentifierCode]-[ancestor::cac:ProcurementProjectLot/cbc:ID schemeName="Lot"]`.
  - Set its `.field` to "awa-cri-num".
  - Set its `.name` to "Award Criterion Number".

```xml
<efac:FieldsPrivacy>
  <efbc:FieldIdentifierCode listName="non-publication-identifier">awa-cri-num</efbc:FieldIdentifierCode>
</efac:FieldsPrivacy>
```

```json
{
  "withheldInformation": [
    {
      "field": "awa-cri-num",
      "id": "awa-cri-num-LOT-0001",
      "name": "Award Criterion Number"
    }
  ]
}
```

</td>
      </tr>
      <tr id="BT-195(BT-541)-LotsGroup">
        <td class="field break-all">
            <p><b>BT-195(BT-541)-LotsGroup</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/withheld-publication.html#lotsGroupOfLotsLevelSection"></a><br>Unpublished Identifier</p><p><i>BT-195:</i> Identifier of the field that shall not be immediately published. Only fields concerning the Result value and groups of fields concerning the Tender and Procedure Lot Result can be unpublished. In the case of the European Parliament and Council Directive 2014/25/EU, the award criteria, the procurement procedure, certain dates and in certain cases information about the nature and quantity of a service can be unpublished as well.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='LotsGroup']/cac:TenderingTerms/cac:AwardingTerms/cac:AwardingCriterion/cac:SubordinateAwardingCriterion/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:AwardCriterionParameter/efac:FieldsPrivacy[efbc:FieldIdentifierCode/text()='awa-cri-num']/efbc:FieldIdentifierCode</span></code>
        </td>
        <td class="mapping">

- Add a `withheldInformationItem` to the `withheldInformation` array, and:
  - Set its `.id` to `[efbc:FieldIdentifierCode]-[ancestor::cac:ProcurementProjectLot/cbc:ID schemeName="LotsGroup"]`.
  - Set its `.field` to "awa-cri-num".
  - Set its `.name` to "Award Criterion Number".

```xml
<efac:FieldsPrivacy>
  <efbc:FieldIdentifierCode listName="non-publication-identifier">awa-cri-num</efbc:FieldIdentifierCode>
</efac:FieldsPrivacy>
```

```json
{
  "withheldInformation": [
    {
      "field": "awa-cri-num",
      "id": "awa-cri-num-GLO-0001",
      "name": "Award Criterion Number"
    }
  ]
}
```

</td>
      </tr>
      <tr id="BT-195(BT-5421)-Lot">
        <td class="field break-all">
            <p><b>BT-195(BT-5421)-Lot</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/withheld-publication.html#lotsGroupOfLotsLevelSection"></a><br>Unpublished Identifier</p><p><i>BT-195:</i> Identifier of the field that shall not be immediately published. Only fields concerning the Result value and groups of fields concerning the Tender and Procedure Lot Result can be unpublished. In the case of the European Parliament and Council Directive 2014/25/EU, the award criteria, the procurement procedure, certain dates and in certain cases information about the nature and quantity of a service can be unpublished as well.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='Lot']/cac:TenderingTerms/cac:AwardingTerms/cac:AwardingCriterion/cac:SubordinateAwardingCriterion/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:AwardCriterionParameter[efbc:ParameterCode/@listName='number-weight']/efac:FieldsPrivacy[efbc:FieldIdentifierCode/text()='awa-cri-wei']/efbc:FieldIdentifierCode</span></code>
        </td>
        <td class="mapping">

- Add a `withheldInformationItem` to the `withheldInformation` array, and:
  - Set its `.id` to `[efbc:FieldIdentifierCode]-[ancestor::cac:ProcurementProjectLot/cbc:ID schemeName="Lot"]`.
  - Set its `.field` to "awa-cri-wei".
  - Set its `.name` to "Award Criterion Number Weight".

```xml
<efac:FieldsPrivacy>
  <efbc:FieldIdentifierCode listName="non-publication-identifier">awa-cri-wei</efbc:FieldIdentifierCode>
</efac:FieldsPrivacy>
```

```json
{
  "withheldInformation": [
    {
      "field": "awa-cri-wei",
      "id": "awa-cri-wei-LOT-0001",
      "name": "Award Criterion Number Weight"
    }
  ]
}
```

</td>
      </tr>
      <tr id="BT-195(BT-5421)-LotsGroup">
        <td class="field break-all">
            <p><b>BT-195(BT-5421)-LotsGroup</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/withheld-publication.html#lotsGroupOfLotsLevelSection"></a><br>Unpublished Identifier</p><p><i>BT-195:</i> Identifier of the field that shall not be immediately published. Only fields concerning the Result value and groups of fields concerning the Tender and Procedure Lot Result can be unpublished. In the case of the European Parliament and Council Directive 2014/25/EU, the award criteria, the procurement procedure, certain dates and in certain cases information about the nature and quantity of a service can be unpublished as well.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='LotsGroup']/cac:TenderingTerms/cac:AwardingTerms/cac:AwardingCriterion/cac:SubordinateAwardingCriterion/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:AwardCriterionParameter[efbc:ParameterCode/@listName='number-weight']/efac:FieldsPrivacy[efbc:FieldIdentifierCode/text()='awa-cri-wei']/efbc:FieldIdentifierCode</span></code>
        </td>
        <td class="mapping">

- Add a `withheldInformationItem` to the `withheldInformation` array, and:
  - Set its `.id` to `[efbc:FieldIdentifierCode]-[ancestor::cac:ProcurementProjectLot/cbc:ID schemeName="LotsGroup"]`.
  - Set its `.field` to "awa-cri-wei".
  - Set its `.name` to "Award Criterion Number Weight".

```xml
<efac:FieldsPrivacy>
  <efbc:FieldIdentifierCode listName="non-publication-identifier">awa-cri-wei</efbc:FieldIdentifierCode>
</efac:FieldsPrivacy>
```

```json
{
  "withheldInformation": [
    {
      "field": "awa-cri-wei",
      "id": "awa-cri-wei-GLO-0001",
      "name": "Award Criterion Number Weight"
    }
  ]
}
```

</td>
      </tr>
      <tr id="BT-195(BT-5422)-Lot">
        <td class="field break-all">
            <p><b>BT-195(BT-5422)-Lot</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/withheld-publication.html#lotsGroupOfLotsLevelSection"></a><br>Unpublished Identifier</p><p><i>BT-195:</i> Identifier of the field that shall not be immediately published. Only fields concerning the Result value and groups of fields concerning the Tender and Procedure Lot Result can be unpublished. In the case of the European Parliament and Council Directive 2014/25/EU, the award criteria, the procurement procedure, certain dates and in certain cases information about the nature and quantity of a service can be unpublished as well.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='Lot']/cac:TenderingTerms/cac:AwardingTerms/cac:AwardingCriterion/cac:SubordinateAwardingCriterion/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:AwardCriterionParameter[efbc:ParameterCode/@listName='number-fixed']/efac:FieldsPrivacy[efbc:FieldIdentifierCode/text()='awa-cri-fix']/efbc:FieldIdentifierCode</span></code>
        </td>
        <td class="mapping">

- Add a `withheldInformationItem` to the `withheldInformation` array, and:
  - Set its `.id` to `[efbc:FieldIdentifierCode]-[ancestor::cac:ProcurementProjectLot/cbc:ID schemeName="Lot"]`.
  - Set its `.field` to "awa-cri-fix".
  - Set its `.name` to "Award Criterion Number Fixed".

```xml
<efac:FieldsPrivacy>
  <efbc:FieldIdentifierCode listName="non-publication-identifier">awa-cri-fix</efbc:FieldIdentifierCode>
</efac:FieldsPrivacy>
```

```json
{
  "withheldInformation": [
    {
      "field": "awa-cri-fix",
      "id": "awa-cri-fix-LOT-0001",
      "name": "Award Criterion Number Fixed"
    }
  ]
}
```

</td>
      </tr>
      <tr id="BT-195(BT-5422)-LotsGroup">
        <td class="field break-all">
            <p><b>BT-195(BT-5422)-LotsGroup</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/withheld-publication.html#lotsGroupOfLotsLevelSection"></a><br>Unpublished Identifier</p><p><i>BT-195:</i> Identifier of the field that shall not be immediately published. Only fields concerning the Result value and groups of fields concerning the Tender and Procedure Lot Result can be unpublished. In the case of the European Parliament and Council Directive 2014/25/EU, the award criteria, the procurement procedure, certain dates and in certain cases information about the nature and quantity of a service can be unpublished as well.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='LotsGroup']/cac:TenderingTerms/cac:AwardingTerms/cac:AwardingCriterion/cac:SubordinateAwardingCriterion/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:AwardCriterionParameter[efbc:ParameterCode/@listName='number-fixed']/efac:FieldsPrivacy[efbc:FieldIdentifierCode/text()='awa-cri-fix']/efbc:FieldIdentifierCode</span></code>
        </td>
        <td class="mapping">

- Add a `withheldInformationItem` to the `withheldInformation` array, and:
  - Set its `.id` to `[efbc:FieldIdentifierCode]-[ancestor::cac:ProcurementProjectLot/cbc:ID schemeName="LotsGroup"]`.
  - Set its `.field` to "awa-cri-fix".
  - Set its `.name` to "Award Criterion Number Fixed".

```xml
<efac:FieldsPrivacy>
  <efbc:FieldIdentifierCode listName="non-publication-identifier">awa-cri-fix</efbc:FieldIdentifierCode>
</efac:FieldsPrivacy>
```

```json
{
  "withheldInformation": [
    {
      "field": "awa-cri-fix",
      "id": "awa-cri-fix-GLO-0001",
      "name": "Award Criterion Number Fixed"
    }
  ]
}
```

</td>
      </tr>
      <tr id="BT-195(BT-5423)-Lot">
        <td class="field break-all">
            <p><b>BT-195(BT-5423)-Lot</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/withheld-publication.html#lotsGroupOfLotsLevelSection"></a><br>Unpublished Identifier</p><p><i>BT-195:</i> Identifier of the field that shall not be immediately published. Only fields concerning the Result value and groups of fields concerning the Tender and Procedure Lot Result can be unpublished. In the case of the European Parliament and Council Directive 2014/25/EU, the award criteria, the procurement procedure, certain dates and in certain cases information about the nature and quantity of a service can be unpublished as well.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='Lot']/cac:TenderingTerms/cac:AwardingTerms/cac:AwardingCriterion/cac:SubordinateAwardingCriterion/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:AwardCriterionParameter[efbc:ParameterCode/@listName='number-threshold']/efac:FieldsPrivacy[efbc:FieldIdentifierCode/text()='awa-cri-thr']/efbc:FieldIdentifierCode</span></code>
        </td>
        <td class="mapping">

- Add a `withheldInformationItem` to the `withheldInformation` array, and:
  - Set its `.id` to `[efbc:FieldIdentifierCode]-[ancestor::cac:ProcurementProjectLot/cbc:ID schemeName="Lot"]`.
  - Set its `.field` to "awa-cri-thr".
  - Set its `.name` to "Award Criterion Number Threshold".

```xml
<efac:FieldsPrivacy>
  <efbc:FieldIdentifierCode listName="non-publication-identifier">awa-cri-thr</efbc:FieldIdentifierCode>
</efac:FieldsPrivacy>
```

```json
{
  "withheldInformation": [
    {
      "field": "awa-cri-thr",
      "id": "awa-cri-thr-LOT-0001",
      "name": "Award Criterion Number Threshold"
    }
  ]
}
```

</td>
      </tr>
      <tr id="BT-195(BT-5423)-LotsGroup">
        <td class="field break-all">
            <p><b>BT-195(BT-5423)-LotsGroup</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/withheld-publication.html#lotsGroupOfLotsLevelSection"></a><br>Unpublished Identifier</p><p><i>BT-195:</i> Identifier of the field that shall not be immediately published. Only fields concerning the Result value and groups of fields concerning the Tender and Procedure Lot Result can be unpublished. In the case of the European Parliament and Council Directive 2014/25/EU, the award criteria, the procurement procedure, certain dates and in certain cases information about the nature and quantity of a service can be unpublished as well.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='LotsGroup']/cac:TenderingTerms/cac:AwardingTerms/cac:AwardingCriterion/cac:SubordinateAwardingCriterion/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:AwardCriterionParameter[efbc:ParameterCode/@listName='number-threshold']/efac:FieldsPrivacy[efbc:FieldIdentifierCode/text()='awa-cri-thr']/efbc:FieldIdentifierCode</span></code>
        </td>
        <td class="mapping">

- Add a `withheldInformationItem` to the `withheldInformation` array, and:
  - Set its `.id` to `[efbc:FieldIdentifierCode]-[ancestor::cac:ProcurementProjectLot/cbc:ID schemeName="LotsGroup"]`.
  - Set its `.field` to "awa-cri-thr".
  - Set its `.name` to "Award Criterion Number Threshold".

```xml
<efac:FieldsPrivacy>
  <efbc:FieldIdentifierCode listName="non-publication-identifier">awa-cri-thr</efbc:FieldIdentifierCode>
</efac:FieldsPrivacy>
```

```json
{
  "withheldInformation": [
    {
      "field": "awa-cri-thr",
      "id": "awa-cri-thr-GLO-0001",
      "name": "Award Criterion Number Threshold"
    }
  ]
}
```

</td>
      </tr>
      <tr id="BT-195(BT-543)-Lot">
        <td class="field break-all">
            <p><b>BT-195(BT-543)-Lot</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/withheld-publication.html#lotsGroupOfLotsLevelSection"></a><br>Unpublished Identifier</p><p><i>BT-195:</i> Identifier of the field that shall not be immediately published. Only fields concerning the Result value and groups of fields concerning the Tender and Procedure Lot Result can be unpublished. In the case of the European Parliament and Council Directive 2014/25/EU, the award criteria, the procurement procedure, certain dates and in certain cases information about the nature and quantity of a service can be unpublished as well.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='Lot']/cac:TenderingTerms/cac:AwardingTerms/cac:AwardingCriterion/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:FieldsPrivacy[efbc:FieldIdentifierCode/text()='awa-cri-com']/efbc:FieldIdentifierCode</span></code>
        </td>
        <td class="mapping">

- Add a `withheldInformationItem` to the `withheldInformation` array, and:
  - Set its `.id` to `[efbc:FieldIdentifierCode]-[ancestor::cac:ProcurementProjectLot/cbc:ID schemeName="Lot"]`.
  - Set its `.field` to "awa-cri-com".
  - Set its `.name` to "Award Criteria Complicated".

```xml
<efac:FieldsPrivacy>
  <efbc:FieldIdentifierCode listName="non-publication-identifier">awa-cri-com</efbc:FieldIdentifierCode>
</efac:FieldsPrivacy>
```

```json
{
  "withheldInformation": [
    {
      "field": "awa-cri-com",
      "id": "awa-cri-com-LOT-0001",
      "name": "Award Criteria Complicated"
    }
  ]
}
```

</td>
      </tr>
      <tr id="BT-195(BT-543)-LotsGroup">
        <td class="field break-all">
            <p><b>BT-195(BT-543)-LotsGroup</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/withheld-publication.html#lotsGroupOfLotsLevelSection"></a><br>Unpublished Identifier</p><p><i>BT-195:</i> Identifier of the field that shall not be immediately published. Only fields concerning the Result value and groups of fields concerning the Tender and Procedure Lot Result can be unpublished. In the case of the European Parliament and Council Directive 2014/25/EU, the award criteria, the procurement procedure, certain dates and in certain cases information about the nature and quantity of a service can be unpublished as well.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='LotsGroup']/cac:TenderingTerms/cac:AwardingTerms/cac:AwardingCriterion/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:FieldsPrivacy[efbc:FieldIdentifierCode/text()='awa-cri-com']/efbc:FieldIdentifierCode</span></code>
        </td>
        <td class="mapping">

- Add a `withheldInformationItem` to the `withheldInformation` array, and:
  - Set its `.id` to `[efbc:FieldIdentifierCode]-[ancestor::cac:ProcurementProjectLot/cbc:ID schemeName="LotsGroup"]`.
  - Set its `.field` to "awa-cri-com".
  - Set its `.name` to "Award Criteria Complicated".

```xml
<efac:FieldsPrivacy>
  <efbc:FieldIdentifierCode listName="non-publication-identifier">awa-cri-com</efbc:FieldIdentifierCode>
</efac:FieldsPrivacy>
```

```json
{
  "withheldInformation": [
    {
      "field": "awa-cri-com",
      "id": "awa-cri-com-GLO-0001",
      "name": "Award Criteria Complicated"
    }
  ]
}
```

</td>
      </tr>
      <tr id="BT-195(BT-553)-Tender">
        <td class="field break-all">
            <p><b>BT-195(BT-553)-Tender</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/withheld-publication.html#lotTenderLevelSection"></a><br>Unpublished Identifier</p><p><i>BT-195:</i> Identifier of the field that shall not be immediately published. Only fields concerning the Result value and groups of fields concerning the Tender and Procedure Lot Result can be unpublished. In the case of the European Parliament and Council Directive 2014/25/EU, the award criteria, the procurement procedure, certain dates and in certain cases information about the nature and quantity of a service can be unpublished as well.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:NoticeResult/efac:LotTender/efac:SubcontractingTerm/efac:FieldsPrivacy[efbc:FieldIdentifierCode/text()='sub-val']/efbc:FieldIdentifierCode</span></code>
        </td>
        <td class="mapping">

- Add a `withheldInformationItem` to the `withheldInformation` array, and:
  - Set its `.id` to `[efbc:FieldIdentifierCode]-[ancestor::efac:LotTender/cbc:ID]`.
  - Set its `.field` to "sub-val".
  - Set its `.name` to "Subcontracting Value".

```xml
<efac:FieldsPrivacy>
  <efbc:FieldIdentifierCode listName="non-publication-identifier">sub-val</efbc:FieldIdentifierCode>
</efac:FieldsPrivacy>
```

```json
{
  "withheldInformation": [
    {
      "field": "sub-val",
      "id": "sub-val-TEN-0001",
      "name": "Subcontracting Value"
    }
  ]
}
```

</td>
      </tr>
      <tr id="BT-195(BT-554)-Tender">
        <td class="field break-all">
            <p><b>BT-195(BT-554)-Tender</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/withheld-publication.html#lotTenderLevelSection"></a><br>Unpublished Identifier</p><p><i>BT-195:</i> Identifier of the field that shall not be immediately published. Only fields concerning the Result value and groups of fields concerning the Tender and Procedure Lot Result can be unpublished. In the case of the European Parliament and Council Directive 2014/25/EU, the award criteria, the procurement procedure, certain dates and in certain cases information about the nature and quantity of a service can be unpublished as well.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:NoticeResult/efac:LotTender/efac:SubcontractingTerm/efac:FieldsPrivacy[efbc:FieldIdentifierCode/text()='sub-des']/efbc:FieldIdentifierCode</span></code>
        </td>
        <td class="mapping">

- Add a `withheldInformationItem` to the `withheldInformation` array, and:
  - Set its `.id` to `[efbc:FieldIdentifierCode]-[ancestor::efac:LotTender/cbc:ID]`.
  - Set its `.field` to "sub-des".
  - Set its `.name` to "Subcontracting Description".

```xml
<efac:FieldsPrivacy>
  <efbc:FieldIdentifierCode listName="non-publication-identifier">sub-des</efbc:FieldIdentifierCode>
</efac:FieldsPrivacy>
```

```json
{
  "withheldInformation": [
    {
      "field": "sub-des",
      "id": "sub-des-TEN-0001",
      "name": "Subcontracting Description"
    }
  ]
}
```

</td>
      </tr>
      <tr id="BT-195(BT-555)-Tender">
        <td class="field break-all">
            <p><b>BT-195(BT-555)-Tender</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/withheld-publication.html#lotTenderLevelSection"></a><br>Unpublished Identifier</p><p><i>BT-195:</i> Identifier of the field that shall not be immediately published. Only fields concerning the Result value and groups of fields concerning the Tender and Procedure Lot Result can be unpublished. In the case of the European Parliament and Council Directive 2014/25/EU, the award criteria, the procurement procedure, certain dates and in certain cases information about the nature and quantity of a service can be unpublished as well.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:NoticeResult/efac:LotTender/efac:SubcontractingTerm/efac:FieldsPrivacy[efbc:FieldIdentifierCode/text()='sub-per']/efbc:FieldIdentifierCode</span></code>
        </td>
        <td class="mapping">

- Add a `withheldInformationItem` to the `withheldInformation` array, and:
  - Set its `.id` to `[efbc:FieldIdentifierCode]-[ancestor::efac:LotTender/cbc:ID]`.
  - Set its `.field` to "sub-per".
  - Set its `.name` to "Subcontracting Percentage".

```xml
<efac:FieldsPrivacy>
  <efbc:FieldIdentifierCode listName="non-publication-identifier">sub-per</efbc:FieldIdentifierCode>
</efac:FieldsPrivacy>
```

```json
{
  "withheldInformation": [
    {
      "field": "sub-per",
      "id": "sub-per-TEN-0001",
      "name": "Subcontracting Percentage"
    }
  ]
}
```

</td>
      </tr>
      <tr id="BT-195(BT-556)-NoticeResult">
        <td class="field break-all">
            <p><b>BT-195(BT-556)-NoticeResult</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/withheld-publication.html#_notice_result_level"></a><br>Unpublished Identifier</p><p><i>BT-195:</i> Identifier of the field that shall not be immediately published. Only fields concerning the Result value and groups of fields concerning the Tender and Procedure Lot Result can be unpublished. In the case of the European Parliament and Council Directive 2014/25/EU, the award criteria, the procurement procedure, certain dates and in certain cases information about the nature and quantity of a service can be unpublished as well.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:NoticeResult/efac:GroupFramework/efac:FieldsPrivacy[efbc:FieldIdentifierCode/text()='gro-max-ide']/efbc:FieldIdentifierCode</span></code>
        </td>
        <td class="mapping">

Discard.

```xml
<efac:FieldsPrivacy>
  <efbc:FieldIdentifierCode listName="non-publication-identifier">gro-max-ide</efbc:FieldIdentifierCode>
</efac:FieldsPrivacy>
```



</td>
      </tr>
      <tr id="BT-195(BT-635)-LotResult">
        <td class="field break-all">
            <p><b>BT-195(BT-635)-LotResult</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/withheld-publication.html#lotResultLevelSection"></a><br>Unpublished Identifier</p><p><i>BT-195:</i> Identifier of the field that shall not be immediately published. Only fields concerning the Result value and groups of fields concerning the Tender and Procedure Lot Result can be unpublished. In the case of the European Parliament and Council Directive 2014/25/EU, the award criteria, the procurement procedure, certain dates and in certain cases information about the nature and quantity of a service can be unpublished as well.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:NoticeResult/efac:LotResult/efac:AppealRequestsStatistics[efbc:StatisticsCode/@listName='irregularity-type']/efac:FieldsPrivacy[efbc:FieldIdentifierCode/text()='buy-rev-cou']/efbc:FieldIdentifierCode</span></code>
        </td>
        <td class="mapping">

- Add a `withheldInformationItem` to the `withheldInformation` array, and:
  - Set its `.id` to `[efbc:FieldIdentifierCode]-[ancestor::efac:LotResult/cbc:ID]`.
  - Set its `.field` to "buy-rev-cou".
  - Set its `.name` to "Buyer Review Request Count".

```xml
<efac:FieldsPrivacy>
  <efbc:FieldIdentifierCode listName="non-publication-identifier">buy-rev-cou</efbc:FieldIdentifierCode>
</efac:FieldsPrivacy>
```

```json
{
  "withheldInformation": [
    {
      "field": "buy-rev-cou",
      "id": "buy-rev-cou-RES-0001",
      "name": "Buyer Review Request Count"
    }
  ]
}
```

</td>
      </tr>
      <tr id="BT-195(BT-636)-LotResult">
        <td class="field break-all">
            <p><b>BT-195(BT-636)-LotResult</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/withheld-publication.html#lotResultLevelSection"></a><br>Unpublished Identifier</p><p><i>BT-195:</i> Identifier of the field that shall not be immediately published. Only fields concerning the Result value and groups of fields concerning the Tender and Procedure Lot Result can be unpublished. In the case of the European Parliament and Council Directive 2014/25/EU, the award criteria, the procurement procedure, certain dates and in certain cases information about the nature and quantity of a service can be unpublished as well.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:NoticeResult/efac:LotResult/efac:AppealRequestsStatistics[efbc:StatisticsCode/@listName='irregularity-type']/efac:FieldsPrivacy[efbc:FieldIdentifierCode/text()='buy-rev-typ']/efbc:FieldIdentifierCode</span></code>
        </td>
        <td class="mapping">

- Add a `withheldInformationItem` to the `withheldInformation` array, and:
  - Set its `.id` to `[efbc:FieldIdentifierCode]-[ancestor::efac:LotResult/cbc:ID]`.
  - Set its `.field` to "buy-rev-typ".
  - Set its `.name` to "Buyer Review Requests Irregularity Type".

```xml
<efac:FieldsPrivacy>
  <efbc:FieldIdentifierCode listName="non-publication-identifier">buy-rev-typ</efbc:FieldIdentifierCode>
</efac:FieldsPrivacy>
```

```json
{
  "withheldInformation": [
    {
      "field": "buy-rev-typ",
      "id": "buy-rev-typ-RES-0001",
      "name": "Buyer Review Request Irregularity Type"
    }
  ]
}
```

</td>
      </tr>
      <tr id="BT-195(BT-709)-LotResult">
        <td class="field break-all">
            <p><b>BT-195(BT-709)-LotResult</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/withheld-publication.html#lotResultLevelSection"></a><br>Unpublished Identifier</p><p><i>BT-195:</i> Identifier of the field that shall not be immediately published. Only fields concerning the Result value and groups of fields concerning the Tender and Procedure Lot Result can be unpublished. In the case of the European Parliament and Council Directive 2014/25/EU, the award criteria, the procurement procedure, certain dates and in certain cases information about the nature and quantity of a service can be unpublished as well.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:NoticeResult/efac:LotResult/efac:FrameworkAgreementValues/efac:FieldsPrivacy[efbc:FieldIdentifierCode/text()='max-val']/efbc:FieldIdentifierCode</span></code>
        </td>
        <td class="mapping">

- Add a `withheldInformationItem` to the `withheldInformation` array, and:
  - Set its `.id` to `[efbc:FieldIdentifierCode]-[ancestor::efac:LotResult/cbc:ID]`.
  - Set its `.field` to "max-val".
  - Set its `.name` to "Maximum Value".

```xml
<efac:FieldsPrivacy>
  <efbc:FieldIdentifierCode listName="non-publication-identifier">max-val</efbc:FieldIdentifierCode>
</efac:FieldsPrivacy>
```

```json
{
  "withheldInformation": [
    {
      "field": "max-val",
      "id": "max-val-RES-0001",
      "name": "Maximum Value"
    }
  ]
}
```

</td>
      </tr>
      <tr id="BT-195(BT-710)-LotResult">
        <td class="field break-all">
            <p><b>BT-195(BT-710)-LotResult</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/withheld-publication.html#lotResultLevelSection"></a><br>Unpublished Identifier</p><p><i>BT-195:</i> Identifier of the field that shall not be immediately published. Only fields concerning the Result value and groups of fields concerning the Tender and Procedure Lot Result can be unpublished. In the case of the European Parliament and Council Directive 2014/25/EU, the award criteria, the procurement procedure, certain dates and in certain cases information about the nature and quantity of a service can be unpublished as well.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:NoticeResult/efac:LotResult/efac:FieldsPrivacy[efbc:FieldIdentifierCode/text()='ten-val-low']/efbc:FieldIdentifierCode</span></code>
        </td>
        <td class="mapping">

- Add a `withheldInformationItem` to the `withheldInformation` array, and:
  - Set its `.id` to `[efbc:FieldIdentifierCode]-[ancestor::efac:LotResult/cbc:ID]`.
  - Set its `.field` to "ten-val-low".
  - Set its `.name` to "Tender Lowest Value".

```xml
<efac:FieldsPrivacy>
  <efbc:FieldIdentifierCode listName="non-publication-identifier">ten-val-low</efbc:FieldIdentifierCode>
</efac:FieldsPrivacy>
```

```json
{
  "withheldInformation": [
    {
      "field": "ten-val-low",
      "id": "ten-val-low-RES-0001",
      "name": "Tender Lowest Value"
    }
  ]
}
```

</td>
      </tr>
      <tr id="BT-195(BT-711)-LotResult">
        <td class="field break-all">
            <p><b>BT-195(BT-711)-LotResult</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/withheld-publication.html#lotResultLevelSection"></a><br>Unpublished Identifier</p><p><i>BT-195:</i> Identifier of the field that shall not be immediately published. Only fields concerning the Result value and groups of fields concerning the Tender and Procedure Lot Result can be unpublished. In the case of the European Parliament and Council Directive 2014/25/EU, the award criteria, the procurement procedure, certain dates and in certain cases information about the nature and quantity of a service can be unpublished as well.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:NoticeResult/efac:LotResult/efac:FieldsPrivacy[efbc:FieldIdentifierCode/text()='ten-val-hig']/efbc:FieldIdentifierCode</span></code>
        </td>
        <td class="mapping">

- Add a `withheldInformationItem` to the `withheldInformation` array, and:
  - Set its `.id` to `[efbc:FieldIdentifierCode]-[ancestor::efac:LotResult/cbc:ID]`.
  - Set its `.field` to "ten-val-hig".
  - Set its `.name` to "Tender Highest Value".

```xml
<efac:FieldsPrivacy>
  <efbc:FieldIdentifierCode listName="non-publication-identifier">ten-val-hig</efbc:FieldIdentifierCode>
</efac:FieldsPrivacy>
```

```json
{
  "withheldInformation": [
    {
      "field": "ten-val-hig",
      "id": "ten-val-hig-RES-0001",
      "name": "Tender Highest Value"
    }
  ]
}
```

</td>
      </tr>
      <tr id="BT-195(BT-712)-LotResult">
        <td class="field break-all">
            <p><b>BT-195(BT-712)-LotResult</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/withheld-publication.html#lotResultLevelSection"></a><br>Unpublished Identifier</p><p><i>BT-195:</i> Identifier of the field that shall not be immediately published. Only fields concerning the Result value and groups of fields concerning the Tender and Procedure Lot Result can be unpublished. In the case of the European Parliament and Council Directive 2014/25/EU, the award criteria, the procurement procedure, certain dates and in certain cases information about the nature and quantity of a service can be unpublished as well.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:NoticeResult/efac:LotResult/efac:AppealRequestsStatistics[efbc:StatisticsCode/@listName='review-type']/efac:FieldsPrivacy[efbc:FieldIdentifierCode/text()='rev-req']/efbc:FieldIdentifierCode</span></code>
        </td>
        <td class="mapping">

- Add a `withheldInformationItem` to the `withheldInformation` array, and:
  - Set its `.id` to `[efbc:FieldIdentifierCode]-[ancestor::efac:LotResult/cbc:ID]`.
  - Set its `.field` to "rev-req".
  - Set its `.name` to "Buyer Review Complainants".

```xml
<efac:FieldsPrivacy>
  <efbc:FieldIdentifierCode listName="non-publication-identifier">rev-req</efbc:FieldIdentifierCode>
</efac:FieldsPrivacy>
```

```json
{
  "withheldInformation": [
    {
      "field": "rev-req",
      "id": "rev-req-RES-0001",
      "name": "Buyer Review Complainants"
    }
  ]
}
```

</td>
      </tr>
      <tr id="BT-195(BT-720)-Tender">
        <td class="field break-all">
            <p><b>BT-195(BT-720)-Tender</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/withheld-publication.html#lotTenderLevelSection"></a><br>Unpublished Identifier</p><p><i>BT-195:</i> Identifier of the field that shall not be immediately published. Only fields concerning the Result value and groups of fields concerning the Tender and Procedure Lot Result can be unpublished. In the case of the European Parliament and Council Directive 2014/25/EU, the award criteria, the procurement procedure, certain dates and in certain cases information about the nature and quantity of a service can be unpublished as well.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:NoticeResult/efac:LotTender/efac:FieldsPrivacy[efbc:FieldIdentifierCode/text()='win-ten-val']/efbc:FieldIdentifierCode</span></code>
        </td>
        <td class="mapping">

- Add a `withheldInformationItem` to the `withheldInformation` array, and:
  - Set its `.id` to `[efbc:FieldIdentifierCode]-[ancestor::efac:LotTender/cbc:ID]`.
  - Set its `.field` to "win-ten-val".
  - Set its `.name` to "Winning Tender Value".

```xml
<efac:FieldsPrivacy>
  <efbc:FieldIdentifierCode listName="non-publication-identifier">win-ten-val</efbc:FieldIdentifierCode>
</efac:FieldsPrivacy>
```

```json
{
  "withheldInformation": [
    {
      "field": "win-ten-val",
      "id": "win-ten-val-TEN-0001",
      "name": "Winning Tender Value"
    }
  ]
}
```

</td>
      </tr>
      <tr id="BT-195(BT-730)-Tender">
        <td class="field break-all">
            <p><b>BT-195(BT-730)-Tender</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/withheld-publication.html#lotTenderLevelSection"></a><br>Unpublished Identifier</p><p><i>BT-195:</i> Identifier of the field that shall not be immediately published. Only fields concerning the Result value and groups of fields concerning the Tender and Procedure Lot Result can be unpublished. In the case of the European Parliament and Council Directive 2014/25/EU, the award criteria, the procurement procedure, certain dates and in certain cases information about the nature and quantity of a service can be unpublished as well.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:NoticeResult/efac:LotTender/efac:SubcontractingTerm/efac:FieldsPrivacy[efbc:FieldIdentifierCode/text()='sub-val-kno']/efbc:FieldIdentifierCode</span></code>
        </td>
        <td class="mapping">

Discard. BT-730 is discarded as it is implied by BT-553.

```xml
<efac:FieldsPrivacy>
  <efbc:FieldIdentifierCode listName="non-publication-identifier">sub-val-kno</efbc:FieldIdentifierCode>
</efac:FieldsPrivacy>
```



</td>
      </tr>
      <tr id="BT-195(BT-731)-Tender">
        <td class="field break-all">
            <p><b>BT-195(BT-731)-Tender</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/withheld-publication.html#lotTenderLevelSection"></a><br>Unpublished Identifier</p><p><i>BT-195:</i> Identifier of the field that shall not be immediately published. Only fields concerning the Result value and groups of fields concerning the Tender and Procedure Lot Result can be unpublished. In the case of the European Parliament and Council Directive 2014/25/EU, the award criteria, the procurement procedure, certain dates and in certain cases information about the nature and quantity of a service can be unpublished as well.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:NoticeResult/efac:LotTender/efac:SubcontractingTerm/efac:FieldsPrivacy[efbc:FieldIdentifierCode/text()='sub-per-kno']/efbc:FieldIdentifierCode</span></code>
        </td>
        <td class="mapping">

Discard. BT-731 is discarded as it is implied by BT-555.

```xml
<efac:FieldsPrivacy>
  <efbc:FieldIdentifierCode listName="non-publication-identifier">sub-per-kno</efbc:FieldIdentifierCode>
</efac:FieldsPrivacy>
```



</td>
      </tr>
      <tr id="BT-195(BT-733)-Lot">
        <td class="field break-all">
            <p><b>BT-195(BT-733)-Lot</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/withheld-publication.html#lotsGroupOfLotsLevelSection"></a><br>Unpublished Identifier</p><p><i>BT-195:</i> Identifier of the field that shall not be immediately published. Only fields concerning the Result value and groups of fields concerning the Tender and Procedure Lot Result can be unpublished. In the case of the European Parliament and Council Directive 2014/25/EU, the award criteria, the procurement procedure, certain dates and in certain cases information about the nature and quantity of a service can be unpublished as well.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='Lot']/cac:TenderingTerms/cac:AwardingTerms/cac:AwardingCriterion/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:FieldsPrivacy[efbc:FieldIdentifierCode/text()='awa-cri-ord']/efbc:FieldIdentifierCode</span></code>
        </td>
        <td class="mapping">

- Add a `withheldInformationItem` to the `withheldInformation` array, and:
  - Set its `.id` to `[efbc:FieldIdentifierCode]-[ancestor::cac:ProcurementProjectLot/cbc:ID schemeName="Lot"]`.
  - Set its `.field` to "awa-cri-ord".
  - Set its `.name` to "Award Criteria Order Justification".

```xml
<efac:FieldsPrivacy>
  <efbc:FieldIdentifierCode listName="non-publication-identifier">awa-cri-ord</efbc:FieldIdentifierCode>
</efac:FieldsPrivacy>
```

```json
{
  "withheldInformation": [
    {
      "field": "awa-cri-ord",
      "id": "awa-cri-ord-LOT-0001",
      "name": "Award Criteria Order Justification"
    }
  ]
}
```

</td>
      </tr>
      <tr id="BT-195(BT-733)-LotsGroup">
        <td class="field break-all">
            <p><b>BT-195(BT-733)-LotsGroup</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/withheld-publication.html#lotsGroupOfLotsLevelSection"></a><br>Unpublished Identifier</p><p><i>BT-195:</i> Identifier of the field that shall not be immediately published. Only fields concerning the Result value and groups of fields concerning the Tender and Procedure Lot Result can be unpublished. In the case of the European Parliament and Council Directive 2014/25/EU, the award criteria, the procurement procedure, certain dates and in certain cases information about the nature and quantity of a service can be unpublished as well.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='LotsGroup']/cac:TenderingTerms/cac:AwardingTerms/cac:AwardingCriterion/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:FieldsPrivacy[efbc:FieldIdentifierCode/text()='awa-cri-ord']/efbc:FieldIdentifierCode</span></code>
        </td>
        <td class="mapping">

- Add a `withheldInformationItem` to the `withheldInformation` array, and:
  - Set its `.id` to `[efbc:FieldIdentifierCode]-[ancestor::cac:ProcurementProjectLot/cbc:ID schemeName="LotsGroup"]`.
  - Set its `.field` to "awa-cri-ord".
  - Set its `.name` to "Award Criteria Order Justification".

```xml
<efac:FieldsPrivacy>
  <efbc:FieldIdentifierCode listName="non-publication-identifier">awa-cri-ord</efbc:FieldIdentifierCode>
</efac:FieldsPrivacy>
```

```json
{
  "withheldInformation": [
    {
      "field": "awa-cri-ord",
      "id": "awa-cri-ord-GLO-0001",
      "name": "Award Criteria Order Justification"
    }
  ]
}
```

</td>
      </tr>
      <tr id="BT-195(BT-734)-Lot">
        <td class="field break-all">
            <p><b>BT-195(BT-734)-Lot</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/withheld-publication.html#lotsGroupOfLotsLevelSection"></a><br>Unpublished Identifier</p><p><i>BT-195:</i> Identifier of the field that shall not be immediately published. Only fields concerning the Result value and groups of fields concerning the Tender and Procedure Lot Result can be unpublished. In the case of the European Parliament and Council Directive 2014/25/EU, the award criteria, the procurement procedure, certain dates and in certain cases information about the nature and quantity of a service can be unpublished as well.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='Lot']/cac:TenderingTerms/cac:AwardingTerms/cac:AwardingCriterion/cac:SubordinateAwardingCriterion/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:FieldsPrivacy[efbc:FieldIdentifierCode/text()='awa-cri-nam']/efbc:FieldIdentifierCode</span></code>
        </td>
        <td class="mapping">

- Add a `withheldInformationItem` to the `withheldInformation` array, and:
  - Set its `.id` to `[efbc:FieldIdentifierCode]-[ancestor::cac:ProcurementProjectLot/cbc:ID schemeName="Lot"]`.
  - Set its `.field` to "awa-cri-nam".
  - Set its `.name` to "Award Criterion Name".

```xml
<efac:FieldsPrivacy>
  <efbc:FieldIdentifierCode listName="non-publication-identifier">awa-cri-nam</efbc:FieldIdentifierCode>
</efac:FieldsPrivacy>
```

```json
{
  "withheldInformation": [
    {
      "field": "awa-cri-nam",
      "id": "awa-cri-nam-LOT-0001",
      "name": "Award Criteron Name"
    }
  ]
}
```

</td>
      </tr>
      <tr id="BT-195(BT-734)-LotsGroup">
        <td class="field break-all">
            <p><b>BT-195(BT-734)-LotsGroup</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/withheld-publication.html#lotsGroupOfLotsLevelSection"></a><br>Unpublished Identifier</p><p><i>BT-195:</i> Identifier of the field that shall not be immediately published. Only fields concerning the Result value and groups of fields concerning the Tender and Procedure Lot Result can be unpublished. In the case of the European Parliament and Council Directive 2014/25/EU, the award criteria, the procurement procedure, certain dates and in certain cases information about the nature and quantity of a service can be unpublished as well.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='LotsGroup']/cac:TenderingTerms/cac:AwardingTerms/cac:AwardingCriterion/cac:SubordinateAwardingCriterion/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:FieldsPrivacy[efbc:FieldIdentifierCode/text()='awa-cri-nam']/efbc:FieldIdentifierCode</span></code>
        </td>
        <td class="mapping">

- Add a `withheldInformationItem` to the `withheldInformation` array, and:
  - Set its `.id` to `[efbc:FieldIdentifierCode]-[ancestor::cac:ProcurementProjectLot/cbc:ID schemeName="LotsGroup"]`.
  - Set its `.field` to "awa-cri-nam".
  - Set its `.name` to "Award Criterion Name".

```xml
<efac:FieldsPrivacy>
  <efbc:FieldIdentifierCode listName="non-publication-identifier">awa-cri-nam</efbc:FieldIdentifierCode>
</efac:FieldsPrivacy>
```

```json
{
  "withheldInformation": [
    {
      "field": "awa-cri-nam",
      "id": "awa-cri-nam-GLO-0001",
      "name": "Award Criteron Name"
    }
  ]
}
```

</td>
      </tr>
      <tr id="BT-195(BT-759)-LotResult">
        <td class="field break-all">
            <p><b>BT-195(BT-759)-LotResult</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/withheld-publication.html#lotResultLevelSection"></a><br>Unpublished Identifier</p><p><i>BT-195:</i> Identifier of the field that shall not be immediately published. Only fields concerning the Result value and groups of fields concerning the Tender and Procedure Lot Result can be unpublished. In the case of the European Parliament and Council Directive 2014/25/EU, the award criteria, the procurement procedure, certain dates and in certain cases information about the nature and quantity of a service can be unpublished as well.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:NoticeResult/efac:LotResult/efac:ReceivedSubmissionsStatistics/efac:FieldsPrivacy[efbc:FieldIdentifierCode/text()='rec-sub-cou']/efbc:FieldIdentifierCode</span></code>
        </td>
        <td class="mapping">

- Add a `withheldInformationItem` to the `withheldInformation` array, and:
  - Set its `.id` to `[efbc:FieldIdentifierCode]-[ancestor::efac:LotResult/cbc:ID]`.
  - Set its `.field` to "rec-sub-cou".
  - Set its `.name` to "Received Submissions Count".

```xml
<efac:FieldsPrivacy>
  <efbc:FieldIdentifierCode listName="non-publication-identifier">rec-sub-cou</efbc:FieldIdentifierCode>
</efac:FieldsPrivacy>
```

```json
{
  "withheldInformation": [
    {
      "field": "rec-sub-cou",
      "id": "rec-sub-cou-RES-0001",
      "name": "Received Submissions Count"
    }
  ]
}
```

</td>
      </tr>
      <tr id="BT-195(BT-760)-LotResult">
        <td class="field break-all">
            <p><b>BT-195(BT-760)-LotResult</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/withheld-publication.html#lotResultLevelSection"></a><br>Unpublished Identifier</p><p><i>BT-195:</i> Identifier of the field that shall not be immediately published. Only fields concerning the Result value and groups of fields concerning the Tender and Procedure Lot Result can be unpublished. In the case of the European Parliament and Council Directive 2014/25/EU, the award criteria, the procurement procedure, certain dates and in certain cases information about the nature and quantity of a service can be unpublished as well.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:NoticeResult/efac:LotResult/efac:ReceivedSubmissionsStatistics/efac:FieldsPrivacy[efbc:FieldIdentifierCode/text()='rec-sub-typ']/efbc:FieldIdentifierCode</span></code>
        </td>
        <td class="mapping">

- Add a `withheldInformationItem` to the `withheldInformation` array, and:
  - Set its `.id` to `[efbc:FieldIdentifierCode]-[ancestor::efac:LotResult/cbc:ID]`.
  - Set its `.field` to "rec-sub-typ".
  - Set its `.name` to "Received Submissions Type".

```xml
<efac:FieldsPrivacy>
  <efbc:FieldIdentifierCode listName="non-publication-identifier">rec-sub-typ</efbc:FieldIdentifierCode>
</efac:FieldsPrivacy>
```

```json
{
  "withheldInformation": [
    {
      "field": "rec-sub-typ",
      "id": "rec-sub-typ-RES-0001",
      "name": "Received Submissions Type"
    }
  ]
}
```

</td>
      </tr>
      <tr id="BT-195(BT-773)-Tender">
        <td class="field break-all">
            <p><b>BT-195(BT-773)-Tender</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/withheld-publication.html#lotTenderLevelSection"></a><br>Unpublished Identifier</p><p><i>BT-195:</i> Identifier of the field that shall not be immediately published. Only fields concerning the Result value and groups of fields concerning the Tender and Procedure Lot Result can be unpublished. In the case of the European Parliament and Council Directive 2014/25/EU, the award criteria, the procurement procedure, certain dates and in certain cases information about the nature and quantity of a service can be unpublished as well.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:NoticeResult/efac:LotTender/efac:SubcontractingTerm/efac:FieldsPrivacy[efbc:FieldIdentifierCode/text()='sub-con']/efbc:FieldIdentifierCode</span></code>
        </td>
        <td class="mapping">

- Add a `withheldInformationItem` to the `withheldInformation` array, and:
  - Set its `.id` to `[efbc:FieldIdentifierCode]-[ancestor::efac:LotTender/cbc:ID]`.
  - Set its `.field` to "sub-con".
  - Set its `.name` to "Subcontracting".

```xml
<efac:FieldsPrivacy>
  <efbc:FieldIdentifierCode listName="non-publication-identifier">sub-con</efbc:FieldIdentifierCode>
</efac:FieldsPrivacy>
```

```json
{
  "withheldInformation": [
    {
      "field": "sub-con",
      "id": "sub-con-TEN-0001",
      "name": "Subcontracting"
    }
  ]
}
```

</td>
      </tr>
      <tr id="BT-195(BT-88)-Procedure">
        <td class="field break-all">
            <p><b>BT-195(BT-88)-Procedure</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/withheld-publication.html#procedureLevelSection"></a><br>Unpublished Identifier</p><p><i>BT-195:</i> Identifier of the field that shall not be immediately published. Only fields concerning the Result value and groups of fields concerning the Tender and Procedure Lot Result can be unpublished. In the case of the European Parliament and Council Directive 2014/25/EU, the award criteria, the procurement procedure, certain dates and in certain cases information about the nature and quantity of a service can be unpublished as well.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:TenderingProcess/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:FieldsPrivacy[efbc:FieldIdentifierCode/text()='pro-fea']/efbc:FieldIdentifierCode</span></code>
        </td>
        <td class="mapping">

- Add a `withheldInformationItem` to the `withheldInformation` array, and:
  - Set its `.id` to `[efbc:FieldIdentifierCode]-[/*/cbc:ContractFolderID]`.
  - Set its `.field` to "pro-fea".
  - Set its `.name` to "Procedure Features".

```xml
<efac:FieldsPrivacy>
  <efbc:FieldIdentifierCode listName="non-publication-identifier">pro-fea</efbc:FieldIdentifierCode>
</efac:FieldsPrivacy>
```

```json
{
  "withheldInformation": [
    {
      "field": "pro-fea",
      "id": "pro-fea-18d27a53-0109-4f93-9231-6659d931bce0",
      "name": "Procedure Features"
    }
  ]
}
```

</td>
      </tr>
      <tr id="BT-196(BT-09)-Procedure">
        <td class="field break-all">
            <p><b>BT-196(BT-09)-Procedure</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/withheld-publication.html#procedureLevelSection"></a><br>Unpublished Justification Description</p><p><i>BT-196:</i> The justification for not immediately publishing a field and for the choice of a later date at which it can be published.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:TenderingTerms/cac:ProcurementLegislationDocumentReference[cbc:ID/text()='CrossBorderLaw']/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:FieldsPrivacy[efbc:FieldIdentifierCode/text()='cro-bor-law']/efbc:ReasonDescription</span></code>
        </td>
        <td class="mapping">

Get the `withheldInformationItem` object created for BT-195(BT-09)-Procedure and map to its `.rationale`.

```xml
<efac:FieldsPrivacy>
  <efbc:ReasonDescription languageID="ENG">Information delayed publication because of ...</efbc:ReasonDescription>
</efac:FieldsPrivacy>
```

```json
{
  "withheldInformation": [
    {
      "rationale": "Information delayed publication because of ..."
    }
  ]
}
```

</td>
      </tr>
      <tr id="BT-196(BT-105)-Procedure">
        <td class="field break-all">
            <p><b>BT-196(BT-105)-Procedure</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/withheld-publication.html#procedureLevelSection"></a><br>Unpublished Justification Description</p><p><i>BT-196:</i> The justification for not immediately publishing a field and for the choice of a later date at which it can be published.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:TenderingProcess/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:FieldsPrivacy[efbc:FieldIdentifierCode/text()='pro-typ']/efbc:ReasonDescription</span></code>
        </td>
        <td class="mapping">

Get the `withheldInformationItem` object created for BT-195(BT-105)-Procedure and map to its `.rationale`.

```xml
<efac:FieldsPrivacy>
  <efbc:ReasonDescription languageID="ENG">Information delayed publication because of ...</efbc:ReasonDescription>
</efac:FieldsPrivacy>
```

```json
{
  "withheldInformation": [
    {
      "rationale": "Information delayed publication because of ..."
    }
  ]
}
```

</td>
      </tr>
      <tr id="BT-196(BT-106)-Procedure">
        <td class="field break-all">
            <p><b>BT-196(BT-106)-Procedure</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/withheld-publication.html#procedureLevelSection"></a><br>Unpublished Justification Description</p><p><i>BT-196:</i> The justification for not immediately publishing a field and for the choice of a later date at which it can be published.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:TenderingProcess/cac:ProcessJustification[cbc:ProcessReasonCode/@listName='accelerated-procedure']/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:FieldsPrivacy[efbc:FieldIdentifierCode/text()='pro-acc']/efbc:ReasonDescription</span></code>
        </td>
        <td class="mapping">

Get the `withheldInformationItem` object created for BT-195(BT-106)-Procedure and map to its `.rationale`.

```xml
<efac:FieldsPrivacy>
  <efbc:ReasonDescription languageID="ENG">Information delayed publication because of ...</efbc:ReasonDescription>
</efac:FieldsPrivacy>
```

```json
{
  "withheldInformation": [
    {
      "rationale": "Information delayed publication because of ..."
    }
  ]
}
```

</td>
      </tr>
      <tr id="BT-196(BT-1118)-NoticeResult">
        <td class="field break-all">
            <p><b>BT-196(BT-1118)-NoticeResult</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/withheld-publication.html#_notice_result_level"></a><br>Unpublished Justification Description</p><p><i>BT-196:</i> The justification for not immediately publishing a field and for the choice of a later date at which it can be published.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:NoticeResult/efac:FieldsPrivacy[efbc:FieldIdentifierCode/text()='not-app-val']/efbc:ReasonDescription</span></code>
        </td>
        <td class="mapping">

Discard.

```xml
<efac:FieldsPrivacy>
  <efbc:ReasonDescription languageID="ENG">Information delayed publication because of ...</efbc:ReasonDescription>
</efac:FieldsPrivacy>
```



</td>
      </tr>
      <tr id="BT-196(BT-118)-NoticeResult">
        <td class="field break-all">
            <p><b>BT-196(BT-118)-NoticeResult</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/withheld-publication.html#_notice_result_level"></a><br>Unpublished Justification Description</p><p><i>BT-196:</i> The justification for not immediately publishing a field and for the choice of a later date at which it can be published.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:NoticeResult/efac:FieldsPrivacy[efbc:FieldIdentifierCode/text()='not-max-val']/efbc:ReasonDescription</span></code>
        </td>
        <td class="mapping">

Discard.

```xml
<efac:FieldsPrivacy>
  <efbc:ReasonDescription languageID="ENG">Information delayed publication because of ...</efbc:ReasonDescription>
</efac:FieldsPrivacy>
```



</td>
      </tr>
      <tr id="BT-196(BT-1252)-Procedure">
        <td class="field break-all">
            <p><b>BT-196(BT-1252)-Procedure</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/withheld-publication.html#procedureLevelSection"></a><br>Unpublished Justification Description</p><p><i>BT-196:</i> The justification for not immediately publishing a field and for the choice of a later date at which it can be published.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:TenderingProcess/cac:ProcessJustification[cbc:ProcessReasonCode/@listName='direct-award-justification']/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:FieldsPrivacy[efbc:FieldIdentifierCode/text()='dir-awa-pre']/efbc:ReasonDescription</span></code>
        </td>
        <td class="mapping">

Get the `withheldInformationItem` object created for BT-195(BT-1252)-Procedure and map to its `.rationale`.

```xml
<efac:FieldsPrivacy>
  <efbc:ReasonDescription languageID="ENG">Information delayed publication because of ...</efbc:ReasonDescription>
</efac:FieldsPrivacy>
```

```json
{
  "withheldInformation": [
    {
      "rationale": "Information delayed publication because of ..."
    }
  ]
}
```

</td>
      </tr>
      <tr id="BT-196(BT-135)-Procedure">
        <td class="field break-all">
            <p><b>BT-196(BT-135)-Procedure</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/withheld-publication.html#procedureLevelSection"></a><br>Unpublished Justification Description</p><p><i>BT-196:</i> The justification for not immediately publishing a field and for the choice of a later date at which it can be published.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:TenderingProcess/cac:ProcessJustification[cbc:ProcessReasonCode/@listName='direct-award-justification']/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:FieldsPrivacy[efbc:FieldIdentifierCode/text()='dir-awa-tex']/efbc:ReasonDescription</span></code>
        </td>
        <td class="mapping">

Get the `withheldInformationItem` object created for BT-195(BT-135)-Procedure and map to its `.rationale`.

```xml
<efac:FieldsPrivacy>
  <efbc:ReasonDescription languageID="ENG">Information delayed publication because of ...</efbc:ReasonDescription>
</efac:FieldsPrivacy>
```

```json
{
  "withheldInformation": [
    {
      "rationale": "Information delayed publication because of ..."
    }
  ]
}
```

</td>
      </tr>
      <tr id="BT-196(BT-1351)-Procedure">
        <td class="field break-all">
            <p><b>BT-196(BT-1351)-Procedure</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/withheld-publication.html#procedureLevelSection"></a><br>Unpublished Justification Description</p><p><i>BT-196:</i> The justification for not immediately publishing a field and for the choice of a later date at which it can be published.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:TenderingProcess/cac:ProcessJustification[cbc:ProcessReasonCode/@listName='accelerated-procedure']/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:FieldsPrivacy[efbc:FieldIdentifierCode/text()='pro-acc-jus']/efbc:ReasonDescription</span></code>
        </td>
        <td class="mapping">

Get the `withheldInformationItem` object created for BT-195(BT-1351)-Procedure and map to its `.rationale`.

```xml
<efac:FieldsPrivacy>
  <efbc:ReasonDescription languageID="ENG">Information delayed publication because of ...</efbc:ReasonDescription>
</efac:FieldsPrivacy>
```

```json
{
  "withheldInformation": [
    {
      "rationale": "Information delayed publication because of ..."
    }
  ]
}
```

</td>
      </tr>
      <tr id="BT-196(BT-136)-Procedure">
        <td class="field break-all">
            <p><b>BT-196(BT-136)-Procedure</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/withheld-publication.html#procedureLevelSection"></a><br>Unpublished Justification Description</p><p><i>BT-196:</i> The justification for not immediately publishing a field and for the choice of a later date at which it can be published.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:TenderingProcess/cac:ProcessJustification[cbc:ProcessReasonCode/@listName='direct-award-justification']/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:FieldsPrivacy[efbc:FieldIdentifierCode/text()='dir-awa-jus']/efbc:ReasonDescription</span></code>
        </td>
        <td class="mapping">

Get the `withheldInformationItem` object created for BT-195(BT-136)-Procedure and map to its `.rationale`.

```xml
<efac:FieldsPrivacy>
  <efbc:ReasonDescription languageID="ENG">Information delayed publication because of ...</efbc:ReasonDescription>
</efac:FieldsPrivacy>
```

```json
{
  "withheldInformation": [
    {
      "rationale": "Information delayed publication because of ..."
    }
  ]
}
```

</td>
      </tr>
      <tr id="BT-196(BT-142)-LotResult">
        <td class="field break-all">
            <p><b>BT-196(BT-142)-LotResult</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/withheld-publication.html#lotResultLevelSection"></a><br>Unpublished Justification Description</p><p><i>BT-196:</i> The justification for not immediately publishing a field and for the choice of a later date at which it can be published.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:NoticeResult/efac:LotResult/efac:FieldsPrivacy[efbc:FieldIdentifierCode/text()='win-cho']/efbc:ReasonDescription</span></code>
        </td>
        <td class="mapping">

Get the `withheldInformationItem` object created for BT-195(BT-142)-LotResult and `ancestor::efac:LotResult` and map to its `.rationale`.

```xml
<efac:FieldsPrivacy>
  <efbc:ReasonDescription languageID="ENG">Information delayed publication because of ...</efbc:ReasonDescription>
</efac:FieldsPrivacy>
```

```json
{
  "withheldInformation": [
    {
      "rationale": "Information delayed publication because of ..."
    }
  ]
}
```

</td>
      </tr>
      <tr id="BT-196(BT-144)-LotResult">
        <td class="field break-all">
            <p><b>BT-196(BT-144)-LotResult</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/withheld-publication.html#lotResultLevelSection"></a><br>Unpublished Justification Description</p><p><i>BT-196:</i> The justification for not immediately publishing a field and for the choice of a later date at which it can be published.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:NoticeResult/efac:LotResult/efac:DecisionReason/efac:FieldsPrivacy[efbc:FieldIdentifierCode/text()='no-awa-rea']/efbc:ReasonDescription</span></code>
        </td>
        <td class="mapping">

Get the `withheldInformationItem` object created for BT-195(BT-144)-LotResult and `ancestor::efac:LotResult` and map to its `.rationale`.

```xml
<efac:FieldsPrivacy>
  <efbc:ReasonDescription languageID="ENG">Information delayed publication because of ...</efbc:ReasonDescription>
</efac:FieldsPrivacy>
```

```json
{
  "withheldInformation": [
    {
      "rationale": "Information delayed publication because of ..."
    }
  ]
}
```

</td>
      </tr>
      <tr id="BT-196(BT-156)-NoticeResult">
        <td class="field break-all">
            <p><b>BT-196(BT-156)-NoticeResult</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/withheld-publication.html#_notice_result_level"></a><br>Unpublished Justification Description</p><p><i>BT-196:</i> The justification for not immediately publishing a field and for the choice of a later date at which it can be published.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:NoticeResult/efac:GroupFramework/efac:FieldsPrivacy[efbc:FieldIdentifierCode/text()='gro-max-val']/efbc:ReasonDescription</span></code>
        </td>
        <td class="mapping">

Discard.

```xml
<efac:FieldsPrivacy>
  <efbc:ReasonDescription languageID="ENG">Information delayed publication because of ...</efbc:ReasonDescription>
</efac:FieldsPrivacy>
```



</td>
      </tr>
      <tr id="BT-196(BT-1561)-NoticeResult">
        <td class="field break-all">
            <p><b>BT-196(BT-1561)-NoticeResult</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/withheld-publication.html#_notice_result_level"></a><br>Unpublished Justification Description</p><p><i>BT-196:</i> The justification for not immediately publishing a field and for the choice of a later date at which it can be published.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:NoticeResult/efac:GroupFramework/efac:FieldsPrivacy[efbc:FieldIdentifierCode/text()='not-ree-val']/efbc:ReasonDescription</span></code>
        </td>
        <td class="mapping">

Discard.

```xml
<efac:FieldsPrivacy>
  <efbc:ReasonDescription languageID="ENG">Information delayed publication because of ...</efbc:ReasonDescription>
</efac:FieldsPrivacy>
```



</td>
      </tr>
      <tr id="BT-196(BT-160)-Tender">
        <td class="field break-all">
            <p><b>BT-196(BT-160)-Tender</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/withheld-publication.html#lotTenderLevelSection"></a><br>Unpublished Justification Description</p><p><i>BT-196:</i> The justification for not immediately publishing a field and for the choice of a later date at which it can be published.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:NoticeResult/efac:LotTender/efac:ConcessionRevenue/efac:FieldsPrivacy[efbc:FieldIdentifierCode/text()='con-rev-buy']/efbc:ReasonDescription</span></code>
        </td>
        <td class="mapping">

Get the `withheldInformationItem` object created for BT-195(BT-160)-Tender and `ancestor::efac:LotTender` and map to its `.rationale`.

```xml
<efac:FieldsPrivacy>
  <efbc:ReasonDescription languageID="ENG">Information delayed publication because of ...</efbc:ReasonDescription>
</efac:FieldsPrivacy>
```

```json
{
  "withheldInformation": [
    {
      "rationale": "Information delayed publication because of ..."
    }
  ]
}
```

</td>
      </tr>
      <tr id="BT-196(BT-161)-NoticeResult">
        <td class="field break-all">
            <p><b>BT-196(BT-161)-NoticeResult</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/withheld-publication.html#_notice_result_level"></a><br>Unpublished Justification Description</p><p><i>BT-196:</i> The justification for not immediately publishing a field and for the choice of a later date at which it can be published.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:NoticeResult/efac:FieldsPrivacy[efbc:FieldIdentifierCode/text()='not-val']/efbc:ReasonDescription</span></code>
        </td>
        <td class="mapping">

Discard.

```xml
<efac:FieldsPrivacy>
  <efbc:ReasonDescription languageID="ENG">Information delayed publication because of ...</efbc:ReasonDescription>
</efac:FieldsPrivacy>
```



</td>
      </tr>
      <tr id="BT-196(BT-162)-Tender">
        <td class="field break-all">
            <p><b>BT-196(BT-162)-Tender</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/withheld-publication.html#lotTenderLevelSection"></a><br>Unpublished Justification Description</p><p><i>BT-196:</i> The justification for not immediately publishing a field and for the choice of a later date at which it can be published.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:NoticeResult/efac:LotTender/efac:ConcessionRevenue/efac:FieldsPrivacy[efbc:FieldIdentifierCode/text()='con-rev-use']/efbc:ReasonDescription</span></code>
        </td>
        <td class="mapping">

Get the `withheldInformationItem` object created for BT-195(BT-162)-Tender and `ancestor::efac:LotTender` and map to its `.rationale`.

```xml
<efac:FieldsPrivacy>
  <efbc:ReasonDescription languageID="ENG">Information delayed publication because of ...</efbc:ReasonDescription>
</efac:FieldsPrivacy>
```

```json
{
  "withheldInformation": [
    {
      "rationale": "Information delayed publication because of ..."
    }
  ]
}
```

</td>
      </tr>
      <tr id="BT-196(BT-163)-Tender">
        <td class="field break-all">
            <p><b>BT-196(BT-163)-Tender</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/withheld-publication.html#lotTenderLevelSection"></a><br>Unpublished Justification Description</p><p><i>BT-196:</i> The justification for not immediately publishing a field and for the choice of a later date at which it can be published.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:NoticeResult/efac:LotTender/efac:ConcessionRevenue/efac:FieldsPrivacy[efbc:FieldIdentifierCode/text()='val-con-des']/efbc:ReasonDescription</span></code>
        </td>
        <td class="mapping">

Get the `withheldInformationItem` object created for BT-195(BT-163)-Tender and `ancestor::efac:LotTender` and map to its `.rationale`.

```xml
<efac:FieldsPrivacy>
  <efbc:ReasonDescription languageID="ENG">Information delayed publication because of ...</efbc:ReasonDescription>
</efac:FieldsPrivacy>
```

```json
{
  "withheldInformation": [
    {
      "rationale": "Information delayed publication because of ..."
    }
  ]
}
```

</td>
      </tr>
      <tr id="BT-196(BT-171)-Tender">
        <td class="field break-all">
            <p><b>BT-196(BT-171)-Tender</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/withheld-publication.html#lotTenderLevelSection"></a><br>Unpublished Justification Description</p><p><i>BT-196:</i> The justification for not immediately publishing a field and for the choice of a later date at which it can be published.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:NoticeResult/efac:LotTender/efac:FieldsPrivacy[efbc:FieldIdentifierCode/text()='ten-ran']/efbc:ReasonDescription</span></code>
        </td>
        <td class="mapping">

Get the `withheldInformationItem` object created for BT-195(BT-171)-Tender and `ancestor::efac:LotTender` and map to its `.rationale`.

```xml
<efac:FieldsPrivacy>
  <efbc:ReasonDescription languageID="ENG">Information delayed publication because of ...</efbc:ReasonDescription>
</efac:FieldsPrivacy>
```

```json
{
  "withheldInformation": [
    {
      "rationale": "Information delayed publication because of ..."
    }
  ]
}
```

</td>
      </tr>
      <tr id="BT-196(BT-191)-Tender">
        <td class="field break-all">
            <p><b>BT-196(BT-191)-Tender</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/withheld-publication.html#lotTenderLevelSection"></a><br>Unpublished Justification Description</p><p><i>BT-196:</i> The justification for not immediately publishing a field and for the choice of a later date at which it can be published.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:NoticeResult/efac:LotTender/efac:Origin/efac:FieldsPrivacy[efbc:FieldIdentifierCode/text()='cou-ori']/efbc:ReasonDescription</span></code>
        </td>
        <td class="mapping">

Get the `withheldInformationItem` object created for BT-195(BT-191)-Tender and `ancestor::efac:LotTender` and map to its `.rationale`.

```xml
<efac:FieldsPrivacy>
  <efbc:ReasonDescription languageID="ENG">Information delayed publication because of ...</efbc:ReasonDescription>
</efac:FieldsPrivacy>
```

```json
{
  "withheldInformation": [
    {
      "rationale": "Information delayed publication because of ..."
    }
  ]
}
```

</td>
      </tr>
      <tr id="BT-196(BT-193)-Tender">
        <td class="field break-all">
            <p><b>BT-196(BT-193)-Tender</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/withheld-publication.html#lotTenderLevelSection"></a><br>Unpublished Justification Description</p><p><i>BT-196:</i> The justification for not immediately publishing a field and for the choice of a later date at which it can be published.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:NoticeResult/efac:LotTender/efac:FieldsPrivacy[efbc:FieldIdentifierCode/text()='win-ten-var']/efbc:ReasonDescription</span></code>
        </td>
        <td class="mapping">

Get the `withheldInformationItem` object created for BT-195(BT-193)-Tender and `ancestor::efac:LotTender` and map to its `.rationale`.

```xml
<efac:FieldsPrivacy>
  <efbc:ReasonDescription languageID="ENG">Information delayed publication because of ...</efbc:ReasonDescription>
</efac:FieldsPrivacy>
```

```json
{
  "withheldInformation": [
    {
      "rationale": "Information delayed publication because of ..."
    }
  ]
}
```

</td>
      </tr>
      <tr id="BT-196(BT-539)-Lot">
        <td class="field break-all">
            <p><b>BT-196(BT-539)-Lot</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/withheld-publication.html#lotsGroupOfLotsLevelSection"></a><br>Unpublished Justification Description</p><p><i>BT-196:</i> The justification for not immediately publishing a field and for the choice of a later date at which it can be published.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='Lot']/cac:TenderingTerms/cac:AwardingTerms/cac:AwardingCriterion/cac:SubordinateAwardingCriterion/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:FieldsPrivacy[efbc:FieldIdentifierCode/text()='awa-cri-typ']/efbc:ReasonDescription</span></code>
        </td>
        <td class="mapping">

Get the `withheldInformationItem` object created for BT-195(BT-539)-Lot and `ancestor::cac:ProcurementProjectLot[cbc:ID schemeName="Lot"]` and map to its `.rationale`.

```xml
<efac:FieldsPrivacy>
  <efbc:ReasonDescription languageID="ENG">Information delayed publication because of ...</efbc:ReasonDescription>
</efac:FieldsPrivacy>
```

```json
{
  "withheldInformation": [
    {
      "rationale": "Information delayed publication because of ..."
    }
  ]
}
```

</td>
      </tr>
      <tr id="BT-196(BT-539)-LotsGroup">
        <td class="field break-all">
            <p><b>BT-196(BT-539)-LotsGroup</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/withheld-publication.html#lotsGroupOfLotsLevelSection"></a><br>Unpublished Justification Description</p><p><i>BT-196:</i> The justification for not immediately publishing a field and for the choice of a later date at which it can be published.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='LotsGroup']/cac:TenderingTerms/cac:AwardingTerms/cac:AwardingCriterion/cac:SubordinateAwardingCriterion/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:FieldsPrivacy[efbc:FieldIdentifierCode/text()='awa-cri-typ']/efbc:ReasonDescription</span></code>
        </td>
        <td class="mapping">

Get the `withheldInformationItem` object created for BT-195(BT-539)-LotsGroup and `ancestor::cac:ProcurementProjectLot[cbc:ID schemeName="LotsGroup"]` and map to its `.rationale`.

```xml
<efac:FieldsPrivacy>
  <efbc:ReasonDescription languageID="ENG">Information delayed publication because of ...</efbc:ReasonDescription>
</efac:FieldsPrivacy>
```

```json
{
  "withheldInformation": [
    {
      "rationale": "Information delayed publication because of ..."
    }
  ]
}
```

</td>
      </tr>
      <tr id="BT-196(BT-540)-Lot">
        <td class="field break-all">
            <p><b>BT-196(BT-540)-Lot</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/withheld-publication.html#lotsGroupOfLotsLevelSection"></a><br>Unpublished Justification Description</p><p><i>BT-196:</i> The justification for not immediately publishing a field and for the choice of a later date at which it can be published.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='Lot']/cac:TenderingTerms/cac:AwardingTerms/cac:AwardingCriterion/cac:SubordinateAwardingCriterion/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:FieldsPrivacy[efbc:FieldIdentifierCode/text()='awa-cri-des']/efbc:ReasonDescription</span></code>
        </td>
        <td class="mapping">

Get the `withheldInformationItem` object created for BT-195(BT-540)-Lot and `ancestor::cac:ProcurementProjectLot[cbc:ID schemeName="Lot"]` and map to its `.rationale`.

```xml
<efac:FieldsPrivacy>
  <efbc:ReasonDescription languageID="ENG">Information delayed publication because of ...</efbc:ReasonDescription>
</efac:FieldsPrivacy>
```

```json
{
  "withheldInformation": [
    {
      "rationale": "Information delayed publication because of ..."
    }
  ]
}
```

</td>
      </tr>
      <tr id="BT-196(BT-540)-LotsGroup">
        <td class="field break-all">
            <p><b>BT-196(BT-540)-LotsGroup</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/withheld-publication.html#lotsGroupOfLotsLevelSection"></a><br>Unpublished Justification Description</p><p><i>BT-196:</i> The justification for not immediately publishing a field and for the choice of a later date at which it can be published.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='LotsGroup']/cac:TenderingTerms/cac:AwardingTerms/cac:AwardingCriterion/cac:SubordinateAwardingCriterion/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:FieldsPrivacy[efbc:FieldIdentifierCode/text()='awa-cri-des']/efbc:ReasonDescription</span></code>
        </td>
        <td class="mapping">

Get the `withheldInformationItem` object created for BT-195(BT-540)-LotsGroup and `ancestor::cac:ProcurementProjectLot[cbc:ID schemeName="LotsGroup"]` and map to its `.rationale`.

```xml
<efac:FieldsPrivacy>
  <efbc:ReasonDescription languageID="ENG">Information delayed publication because of ...</efbc:ReasonDescription>
</efac:FieldsPrivacy>
```

```json
{
  "withheldInformation": [
    {
      "rationale": "Information delayed publication because of ..."
    }
  ]
}
```

</td>
      </tr>
      <tr id="BT-196(BT-541)-Lot">
        <td class="field break-all">
            <p><b>BT-196(BT-541)-Lot</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/withheld-publication.html#lotsGroupOfLotsLevelSection"></a><br>Unpublished Justification Description</p><p><i>BT-196:</i> The justification for not immediately publishing a field and for the choice of a later date at which it can be published.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='Lot']/cac:TenderingTerms/cac:AwardingTerms/cac:AwardingCriterion/cac:SubordinateAwardingCriterion/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:AwardCriterionParameter/efac:FieldsPrivacy[efbc:FieldIdentifierCode/text()='awa-cri-num']/efbc:ReasonDescription</span></code>
        </td>
        <td class="mapping">

Get the `withheldInformationItem` object created for BT-195(BT-541)-Lot and `ancestor::cac:ProcurementProjectLot[cbc:ID schemeName="Lot"]` and map to its `.rationale`.

```xml
<efac:FieldsPrivacy>
  <efbc:ReasonDescription languageID="ENG">Information delayed publication because of ...</efbc:ReasonDescription>
</efac:FieldsPrivacy>
```

```json
{
  "withheldInformation": [
    {
      "rationale": "Information delayed publication because of ..."
    }
  ]
}
```

</td>
      </tr>
      <tr id="BT-196(BT-541)-LotsGroup">
        <td class="field break-all">
            <p><b>BT-196(BT-541)-LotsGroup</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/withheld-publication.html#lotsGroupOfLotsLevelSection"></a><br>Unpublished Justification Description</p><p><i>BT-196:</i> The justification for not immediately publishing a field and for the choice of a later date at which it can be published.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='LotsGroup']/cac:TenderingTerms/cac:AwardingTerms/cac:AwardingCriterion/cac:SubordinateAwardingCriterion/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:AwardCriterionParameter/efac:FieldsPrivacy[efbc:FieldIdentifierCode/text()='awa-cri-num']/efbc:ReasonDescription</span></code>
        </td>
        <td class="mapping">

Get the `withheldInformationItem` object created for BT-195(BT-541)-LotsGroup and `ancestor::cac:ProcurementProjectLot[cbc:ID schemeName="LotsGroup"]` and map to its `.rationale`.

```xml
<efac:FieldsPrivacy>
  <efbc:ReasonDescription languageID="ENG">Information delayed publication because of ...</efbc:ReasonDescription>
</efac:FieldsPrivacy>
```

```json
{
  "withheldInformation": [
    {
      "rationale": "Information delayed publication because of ..."
    }
  ]
}
```

</td>
      </tr>
      <tr id="BT-196(BT-5421)-Lot">
        <td class="field break-all">
            <p><b>BT-196(BT-5421)-Lot</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/withheld-publication.html#lotsGroupOfLotsLevelSection"></a><br>Unpublished Justification Description</p><p><i>BT-196:</i> The justification for not immediately publishing a field and for the choice of a later date at which it can be published.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='Lot']/cac:TenderingTerms/cac:AwardingTerms/cac:AwardingCriterion/cac:SubordinateAwardingCriterion/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:AwardCriterionParameter[efbc:ParameterCode/@listName='number-weight']/efac:FieldsPrivacy[efbc:FieldIdentifierCode/text()='awa-cri-wei']/efbc:ReasonDescription</span></code>
        </td>
        <td class="mapping">

Get the `withheldInformationItem` object created for BT-195(BT-5421)-Lot and `ancestor::cac:ProcurementProjectLot[cbc:ID schemeName="Lot"]` and map to its `.rationale`.

```xml
<efac:FieldsPrivacy>
  <efbc:ReasonDescription languageID="ENG">Information delayed publication because of ...</efbc:ReasonDescription>
</efac:FieldsPrivacy>
```

```json
{
  "withheldInformation": [
    {
      "rationale": "Information delayed publication because of ..."
    }
  ]
}
```

</td>
      </tr>
      <tr id="BT-196(BT-5421)-LotsGroup">
        <td class="field break-all">
            <p><b>BT-196(BT-5421)-LotsGroup</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/withheld-publication.html#lotsGroupOfLotsLevelSection"></a><br>Unpublished Justification Description</p><p><i>BT-196:</i> The justification for not immediately publishing a field and for the choice of a later date at which it can be published.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='LotsGroup']/cac:TenderingTerms/cac:AwardingTerms/cac:AwardingCriterion/cac:SubordinateAwardingCriterion/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:AwardCriterionParameter[efbc:ParameterCode/@listName='number-weight']/efac:FieldsPrivacy[efbc:FieldIdentifierCode/text()='awa-cri-wei']/efbc:ReasonDescription</span></code>
        </td>
        <td class="mapping">

Get the `withheldInformationItem` object created for BT-195(BT-5421)-LotsGroup and `ancestor::cac:ProcurementProjectLot[cbc:ID schemeName="LotsGroup"]` and map to its `.rationale`.

```xml
<efac:FieldsPrivacy>
  <efbc:ReasonDescription languageID="ENG">Information delayed publication because of ...</efbc:ReasonDescription>
</efac:FieldsPrivacy>
```

```json
{
  "withheldInformation": [
    {
      "rationale": "Information delayed publication because of ..."
    }
  ]
}
```

</td>
      </tr>
      <tr id="BT-196(BT-5422)-Lot">
        <td class="field break-all">
            <p><b>BT-196(BT-5422)-Lot</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/withheld-publication.html#lotsGroupOfLotsLevelSection"></a><br>Unpublished Justification Description</p><p><i>BT-196:</i> The justification for not immediately publishing a field and for the choice of a later date at which it can be published.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='Lot']/cac:TenderingTerms/cac:AwardingTerms/cac:AwardingCriterion/cac:SubordinateAwardingCriterion/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:AwardCriterionParameter[efbc:ParameterCode/@listName='number-fixed']/efac:FieldsPrivacy[efbc:FieldIdentifierCode/text()='awa-cri-fix']/efbc:ReasonDescription</span></code>
        </td>
        <td class="mapping">

Get the `withheldInformationItem` object created for BT-195(BT-5422)-Lot and `ancestor::cac:ProcurementProjectLot[cbc:ID schemeName="Lot"]` and map to its `.rationale`.

```xml
<efac:FieldsPrivacy>
  <efbc:ReasonDescription languageID="ENG">Information delayed publication because of ...</efbc:ReasonDescription>
</efac:FieldsPrivacy>
```

```json
{
  "withheldInformation": [
    {
      "rationale": "Information delayed publication because of ..."
    }
  ]
}
```

</td>
      </tr>
      <tr id="BT-196(BT-5422)-LotsGroup">
        <td class="field break-all">
            <p><b>BT-196(BT-5422)-LotsGroup</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/withheld-publication.html#lotsGroupOfLotsLevelSection"></a><br>Unpublished Justification Description</p><p><i>BT-196:</i> The justification for not immediately publishing a field and for the choice of a later date at which it can be published.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='LotsGroup']/cac:TenderingTerms/cac:AwardingTerms/cac:AwardingCriterion/cac:SubordinateAwardingCriterion/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:AwardCriterionParameter[efbc:ParameterCode/@listName='number-fixed']/efac:FieldsPrivacy[efbc:FieldIdentifierCode/text()='awa-cri-fix']/efbc:ReasonDescription</span></code>
        </td>
        <td class="mapping">

Get the `withheldInformationItem` object created for BT-195(BT-5422)-LotsGroup and `ancestor::cac:ProcurementProjectLot[cbc:ID schemeName="LotsGroup"]` and map to its `.rationale`.

```xml
<efac:FieldsPrivacy>
  <efbc:ReasonDescription languageID="ENG">Information delayed publication because of ...</efbc:ReasonDescription>
</efac:FieldsPrivacy>
```

```json
{
  "withheldInformation": [
    {
      "rationale": "Information delayed publication because of ..."
    }
  ]
}
```

</td>
      </tr>
      <tr id="BT-196(BT-5423)-Lot">
        <td class="field break-all">
            <p><b>BT-196(BT-5423)-Lot</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/withheld-publication.html#lotsGroupOfLotsLevelSection"></a><br>Unpublished Justification Description</p><p><i>BT-196:</i> The justification for not immediately publishing a field and for the choice of a later date at which it can be published.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='Lot']/cac:TenderingTerms/cac:AwardingTerms/cac:AwardingCriterion/cac:SubordinateAwardingCriterion/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:AwardCriterionParameter[efbc:ParameterCode/@listName='number-threshold']/efac:FieldsPrivacy[efbc:FieldIdentifierCode/text()='awa-cri-thr']/efbc:ReasonDescription</span></code>
        </td>
        <td class="mapping">

Get the `withheldInformationItem` object created for BT-195(BT-5423)-Lot and `ancestor::cac:ProcurementProjectLot[cbc:ID schemeName="Lot"]` and map to its `.rationale`.

```xml
<efac:FieldsPrivacy>
  <efbc:ReasonDescription languageID="ENG">Information delayed publication because of ...</efbc:ReasonDescription>
</efac:FieldsPrivacy>
```

```json
{
  "withheldInformation": [
    {
      "rationale": "Information delayed publication because of ..."
    }
  ]
}
```

</td>
      </tr>
      <tr id="BT-196(BT-5423)-LotsGroup">
        <td class="field break-all">
            <p><b>BT-196(BT-5423)-LotsGroup</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/withheld-publication.html#lotsGroupOfLotsLevelSection"></a><br>Unpublished Justification Description</p><p><i>BT-196:</i> The justification for not immediately publishing a field and for the choice of a later date at which it can be published.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='LotsGroup']/cac:TenderingTerms/cac:AwardingTerms/cac:AwardingCriterion/cac:SubordinateAwardingCriterion/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:AwardCriterionParameter[efbc:ParameterCode/@listName='number-threshold']/efac:FieldsPrivacy[efbc:FieldIdentifierCode/text()='awa-cri-thr']/efbc:ReasonDescription</span></code>
        </td>
        <td class="mapping">

Get the `withheldInformationItem` object created for BT-195(BT-5423)-LotsGroup and `ancestor::cac:ProcurementProjectLot[cbc:ID schemeName="LotsGroup"]` and map to its `.rationale`.

```xml
<efac:FieldsPrivacy>
  <efbc:ReasonDescription languageID="ENG">Information delayed publication because of ...</efbc:ReasonDescription>
</efac:FieldsPrivacy>
```

```json
{
  "withheldInformation": [
    {
      "rationale": "Information delayed publication because of ..."
    }
  ]
}
```

</td>
      </tr>
      <tr id="BT-196(BT-543)-Lot">
        <td class="field break-all">
            <p><b>BT-196(BT-543)-Lot</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/withheld-publication.html#lotsGroupOfLotsLevelSection"></a><br>Unpublished Justification Description</p><p><i>BT-196:</i> The justification for not immediately publishing a field and for the choice of a later date at which it can be published.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='Lot']/cac:TenderingTerms/cac:AwardingTerms/cac:AwardingCriterion/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:FieldsPrivacy[efbc:FieldIdentifierCode/text()='awa-cri-com']/efbc:ReasonDescription</span></code>
        </td>
        <td class="mapping">

Get the `withheldInformationItem` object created for BT-195(BT-543)-Lot and `ancestor::cac:ProcurementProjectLot[cbc:ID schemeName="Lot"]` and map to its `.rationale`.

```xml
<efac:FieldsPrivacy>
  <efbc:ReasonDescription languageID="ENG">Information delayed publication because of ...</efbc:ReasonDescription>
</efac:FieldsPrivacy>
```

```json
{
  "withheldInformation": [
    {
      "rationale": "Information delayed publication because of ..."
    }
  ]
}
```

</td>
      </tr>
      <tr id="BT-196(BT-543)-LotsGroup">
        <td class="field break-all">
            <p><b>BT-196(BT-543)-LotsGroup</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/withheld-publication.html#lotsGroupOfLotsLevelSection"></a><br>Unpublished Justification Description</p><p><i>BT-196:</i> The justification for not immediately publishing a field and for the choice of a later date at which it can be published.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='LotsGroup']/cac:TenderingTerms/cac:AwardingTerms/cac:AwardingCriterion/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:FieldsPrivacy[efbc:FieldIdentifierCode/text()='awa-cri-com']/efbc:ReasonDescription</span></code>
        </td>
        <td class="mapping">

Get the `withheldInformationItem` object created for BT-195(BT-543)-LotsGroup and `ancestor::cac:ProcurementProjectLot[cbc:ID schemeName="LotsGroup"]` and map to its `.rationale`.

```xml
<efac:FieldsPrivacy>
  <efbc:ReasonDescription languageID="ENG">Information delayed publication because of ...</efbc:ReasonDescription>
</efac:FieldsPrivacy>
```

```json
{
  "withheldInformation": [
    {
      "rationale": "Information delayed publication because of ..."
    }
  ]
}
```

</td>
      </tr>
      <tr id="BT-196(BT-553)-Tender">
        <td class="field break-all">
            <p><b>BT-196(BT-553)-Tender</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/withheld-publication.html#lotTenderLevelSection"></a><br>Unpublished Justification Description</p><p><i>BT-196:</i> The justification for not immediately publishing a field and for the choice of a later date at which it can be published.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:NoticeResult/efac:LotTender/efac:SubcontractingTerm/efac:FieldsPrivacy[efbc:FieldIdentifierCode/text()='sub-val']/efbc:ReasonDescription</span></code>
        </td>
        <td class="mapping">

Get the `withheldInformationItem` object created for BT-195(BT-553)-Tender and `ancestor::efac:LotTender` and map to its `.rationale`.

```xml
<efac:FieldsPrivacy>
  <efbc:ReasonDescription languageID="ENG">Information delayed publication because of ...</efbc:ReasonDescription>
</efac:FieldsPrivacy>
```

```json
{
  "withheldInformation": [
    {
      "rationale": "Information delayed publication because of ..."
    }
  ]
}
```

</td>
      </tr>
      <tr id="BT-196(BT-554)-Tender">
        <td class="field break-all">
            <p><b>BT-196(BT-554)-Tender</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/withheld-publication.html#lotTenderLevelSection"></a><br>Unpublished Justification Description</p><p><i>BT-196:</i> The justification for not immediately publishing a field and for the choice of a later date at which it can be published.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:NoticeResult/efac:LotTender/efac:SubcontractingTerm/efac:FieldsPrivacy[efbc:FieldIdentifierCode/text()='sub-des']/efbc:ReasonDescription</span></code>
        </td>
        <td class="mapping">

Get the `withheldInformationItem` object created for BT-195(BT-554)-Tender and `ancestor::efac:LotTender` and map to its `.rationale`.

```xml
<efac:FieldsPrivacy>
  <efbc:ReasonDescription languageID="ENG">Information delayed publication because of ...</efbc:ReasonDescription>
</efac:FieldsPrivacy>
```

```json
{
  "withheldInformation": [
    {
      "rationale": "Information delayed publication because of ..."
    }
  ]
}
```

</td>
      </tr>
      <tr id="BT-196(BT-555)-Tender">
        <td class="field break-all">
            <p><b>BT-196(BT-555)-Tender</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/withheld-publication.html#lotTenderLevelSection"></a><br>Unpublished Justification Description</p><p><i>BT-196:</i> The justification for not immediately publishing a field and for the choice of a later date at which it can be published.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:NoticeResult/efac:LotTender/efac:SubcontractingTerm/efac:FieldsPrivacy[efbc:FieldIdentifierCode/text()='sub-per']/efbc:ReasonDescription</span></code>
        </td>
        <td class="mapping">

Get the `withheldInformationItem` object created for BT-195(BT-555)-Tender and `ancestor::efac:LotTender` and map to its `.rationale`.

```xml
<efac:FieldsPrivacy>
  <efbc:ReasonDescription languageID="ENG">Information delayed publication because of ...</efbc:ReasonDescription>
</efac:FieldsPrivacy>
```

```json
{
  "withheldInformation": [
    {
      "rationale": "Information delayed publication because of ..."
    }
  ]
}
```

</td>
      </tr>
      <tr id="BT-196(BT-556)-NoticeResult">
        <td class="field break-all">
            <p><b>BT-196(BT-556)-NoticeResult</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/withheld-publication.html#_notice_result_level"></a><br>Unpublished Justification Description</p><p><i>BT-196:</i> The justification for not immediately publishing a field and for the choice of a later date at which it can be published.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:NoticeResult/efac:GroupFramework/efac:FieldsPrivacy[efbc:FieldIdentifierCode/text()='gro-max-ide']/efbc:ReasonDescription</span></code>
        </td>
        <td class="mapping">

Discard.

```xml
<efac:FieldsPrivacy>
  <efbc:ReasonDescription languageID="ENG">Information delayed publication because of ...</efbc:ReasonDescription>
</efac:FieldsPrivacy>
```



</td>
      </tr>
      <tr id="BT-196(BT-635)-LotResult">
        <td class="field break-all">
            <p><b>BT-196(BT-635)-LotResult</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/withheld-publication.html#lotResultLevelSection"></a><br>Unpublished Justification Description</p><p><i>BT-196:</i> The justification for not immediately publishing a field and for the choice of a later date at which it can be published.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:NoticeResult/efac:LotResult/efac:AppealRequestsStatistics[efbc:StatisticsCode/@listName='irregularity-type']/efac:FieldsPrivacy[efbc:FieldIdentifierCode/text()='buy-rev-cou']/efbc:ReasonDescription</span></code>
        </td>
        <td class="mapping">

Get the `withheldInformationItem` object created for BT-195(BT-635)-LotResult and `ancestor::efac:LotResult` and map to its `.rationale`.

```xml
<efac:FieldsPrivacy>
  <efbc:ReasonDescription languageID="ENG">Information delayed publication because of ...</efbc:ReasonDescription>
</efac:FieldsPrivacy>
```

```json
{
  "withheldInformation": [
    {
      "rationale": "Information delayed publication because of ..."
    }
  ]
}
```

</td>
      </tr>
      <tr id="BT-196(BT-636)-LotResult">
        <td class="field break-all">
            <p><b>BT-196(BT-636)-LotResult</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/withheld-publication.html#lotResultLevelSection"></a><br>Unpublished Justification Description</p><p><i>BT-196:</i> The justification for not immediately publishing a field and for the choice of a later date at which it can be published.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:NoticeResult/efac:LotResult/efac:AppealRequestsStatistics[efbc:StatisticsCode/@listName='irregularity-type']/efac:FieldsPrivacy[efbc:FieldIdentifierCode/text()='buy-rev-typ']/efbc:ReasonDescription</span></code>
        </td>
        <td class="mapping">

Get the `withheldInformationItem` object created for BT-195(BT-636)-LotResult and `ancestor::efac:LotResult` and map to its `.rationale`.

```xml
<efac:FieldsPrivacy>
  <efbc:ReasonDescription languageID="ENG">Information delayed publication because of ...</efbc:ReasonDescription>
</efac:FieldsPrivacy>
```

```json
{
  "withheldInformation": [
    {
      "rationale": "Information delayed publication because of ..."
    }
  ]
}
```

</td>
      </tr>
      <tr id="BT-196(BT-709)-LotResult">
        <td class="field break-all">
            <p><b>BT-196(BT-709)-LotResult</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/withheld-publication.html#lotResultLevelSection"></a><br>Unpublished Justification Description</p><p><i>BT-196:</i> The justification for not immediately publishing a field and for the choice of a later date at which it can be published.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:NoticeResult/efac:LotResult/efac:FrameworkAgreementValues/efac:FieldsPrivacy[efbc:FieldIdentifierCode/text()='max-val']/efbc:ReasonDescription</span></code>
        </td>
        <td class="mapping">

Get the `withheldInformationItem` object created for BT-195(BT-709)-LotResult and `ancestor::efac:LotResult` and map to its `.rationale`.

```xml
<efac:FieldsPrivacy>
  <efbc:ReasonDescription languageID="ENG">Information delayed publication because of ...</efbc:ReasonDescription>
</efac:FieldsPrivacy>
```

```json
{
  "withheldInformation": [
    {
      "rationale": "Information delayed publication because of ..."
    }
  ]
}
```

</td>
      </tr>
      <tr id="BT-196(BT-710)-LotResult">
        <td class="field break-all">
            <p><b>BT-196(BT-710)-LotResult</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/withheld-publication.html#lotResultLevelSection"></a><br>Unpublished Justification Description</p><p><i>BT-196:</i> The justification for not immediately publishing a field and for the choice of a later date at which it can be published.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:NoticeResult/efac:LotResult/efac:FieldsPrivacy[efbc:FieldIdentifierCode/text()='ten-val-low']/efbc:ReasonDescription</span></code>
        </td>
        <td class="mapping">

Get the `withheldInformationItem` object created for BT-195(BT-710)-LotResult and `ancestor::efac:LotResult` and map to its `.rationale`.

```xml
<efac:FieldsPrivacy>
  <efbc:ReasonDescription languageID="ENG">Information delayed publication because of ...</efbc:ReasonDescription>
</efac:FieldsPrivacy>
```

```json
{
  "withheldInformation": [
    {
      "rationale": "Information delayed publication because of ..."
    }
  ]
}
```

</td>
      </tr>
      <tr id="BT-196(BT-711)-LotResult">
        <td class="field break-all">
            <p><b>BT-196(BT-711)-LotResult</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/withheld-publication.html#lotResultLevelSection"></a><br>Unpublished Justification Description</p><p><i>BT-196:</i> The justification for not immediately publishing a field and for the choice of a later date at which it can be published.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:NoticeResult/efac:LotResult/efac:FieldsPrivacy[efbc:FieldIdentifierCode/text()='ten-val-hig']/efbc:ReasonDescription</span></code>
        </td>
        <td class="mapping">

Get the `withheldInformationItem` object created for BT-195(BT-711)-LotResult and `ancestor::efac:LotResult` and map to its `.rationale`.

```xml
<efac:FieldsPrivacy>
  <efbc:ReasonDescription languageID="ENG">Information delayed publication because of ...</efbc:ReasonDescription>
</efac:FieldsPrivacy>
```

```json
{
  "withheldInformation": [
    {
      "rationale": "Information delayed publication because of ..."
    }
  ]
}
```

</td>
      </tr>
      <tr id="BT-196(BT-712)-LotResult">
        <td class="field break-all">
            <p><b>BT-196(BT-712)-LotResult</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/withheld-publication.html#lotResultLevelSection"></a><br>Unpublished Justification Description</p><p><i>BT-196:</i> The justification for not immediately publishing a field and for the choice of a later date at which it can be published.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:NoticeResult/efac:LotResult/efac:AppealRequestsStatistics[efbc:StatisticsCode/@listName='review-type']/efac:FieldsPrivacy[efbc:FieldIdentifierCode/text()='rev-req']/efbc:ReasonDescription</span></code>
        </td>
        <td class="mapping">

Get the `withheldInformationItem` object created for BT-195(BT-712)-LotResult and `ancestor::efac:LotResult` and map to its `.rationale`.

```xml
<efac:FieldsPrivacy>
  <efbc:ReasonDescription languageID="ENG">Information delayed publication because of ...</efbc:ReasonDescription>
</efac:FieldsPrivacy>
```

```json
{
  "withheldInformation": [
    {
      "rationale": "Information delayed publication because of ..."
    }
  ]
}
```

</td>
      </tr>
      <tr id="BT-196(BT-720)-Tender">
        <td class="field break-all">
            <p><b>BT-196(BT-720)-Tender</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/withheld-publication.html#lotTenderLevelSection"></a><br>Unpublished Justification Description</p><p><i>BT-196:</i> The justification for not immediately publishing a field and for the choice of a later date at which it can be published.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:NoticeResult/efac:LotTender/efac:FieldsPrivacy[efbc:FieldIdentifierCode/text()='win-ten-val']/efbc:ReasonDescription</span></code>
        </td>
        <td class="mapping">

Get the `withheldInformationItem` object created for BT-195(BT-720)-Tender and `ancestor::efac:LotTender` and map to its `.rationale`.

```xml
<efac:FieldsPrivacy>
  <efbc:ReasonDescription languageID="ENG">Information delayed publication because of ...</efbc:ReasonDescription>
</efac:FieldsPrivacy>
```

```json
{
  "withheldInformation": [
    {
      "rationale": "Information delayed publication because of ..."
    }
  ]
}
```

</td>
      </tr>
      <tr id="BT-196(BT-730)-Tender">
        <td class="field break-all">
            <p><b>BT-196(BT-730)-Tender</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/withheld-publication.html#lotTenderLevelSection"></a><br>Unpublished Justification Description</p><p><i>BT-196:</i> The justification for not immediately publishing a field and for the choice of a later date at which it can be published.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:NoticeResult/efac:LotTender/efac:SubcontractingTerm/efac:FieldsPrivacy[efbc:FieldIdentifierCode/text()='sub-val-kno']/efbc:ReasonDescription</span></code>
        </td>
        <td class="mapping">

Discard. BT-730 is discarded as it is implied by BT-553.

```xml
<efac:FieldsPrivacy>
  <efbc:ReasonDescription languageID="ENG">Information delayed publication because of ...</efbc:ReasonDescription>
</efac:FieldsPrivacy>
```



</td>
      </tr>
      <tr id="BT-196(BT-731)-Tender">
        <td class="field break-all">
            <p><b>BT-196(BT-731)-Tender</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/withheld-publication.html#lotTenderLevelSection"></a><br>Unpublished Justification Description</p><p><i>BT-196:</i> The justification for not immediately publishing a field and for the choice of a later date at which it can be published.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:NoticeResult/efac:LotTender/efac:SubcontractingTerm/efac:FieldsPrivacy[efbc:FieldIdentifierCode/text()='sub-per-kno']/efbc:ReasonDescription</span></code>
        </td>
        <td class="mapping">

Discard. BT-731 is discarded as it is implied by BT-555.

```xml
<efac:FieldsPrivacy>
  <efbc:ReasonDescription languageID="ENG">Information delayed publication because of ...</efbc:ReasonDescription>
</efac:FieldsPrivacy>
```



</td>
      </tr>
      <tr id="BT-196(BT-733)-Lot">
        <td class="field break-all">
            <p><b>BT-196(BT-733)-Lot</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/withheld-publication.html#lotsGroupOfLotsLevelSection"></a><br>Unpublished Justification Description</p><p><i>BT-196:</i> The justification for not immediately publishing a field and for the choice of a later date at which it can be published.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='Lot']/cac:TenderingTerms/cac:AwardingTerms/cac:AwardingCriterion/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:FieldsPrivacy[efbc:FieldIdentifierCode/text()='awa-cri-ord']/efbc:ReasonDescription</span></code>
        </td>
        <td class="mapping">

Get the `withheldInformationItem` object created for BT-195(BT-733)-Lot and `ancestor::cac:ProcurementProjectLot[cbc:ID schemeName="Lot"]` and map to its `.rationale`.

```xml
<efac:FieldsPrivacy>
  <efbc:ReasonDescription languageID="ENG">Information delayed publication because of ...</efbc:ReasonDescription>
</efac:FieldsPrivacy>
```

```json
{
  "withheldInformation": [
    {
      "rationale": "Information delayed publication because of ..."
    }
  ]
}
```

</td>
      </tr>
      <tr id="BT-196(BT-733)-LotsGroup">
        <td class="field break-all">
            <p><b>BT-196(BT-733)-LotsGroup</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/withheld-publication.html#lotsGroupOfLotsLevelSection"></a><br>Unpublished Justification Description</p><p><i>BT-196:</i> The justification for not immediately publishing a field and for the choice of a later date at which it can be published.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='LotsGroup']/cac:TenderingTerms/cac:AwardingTerms/cac:AwardingCriterion/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:FieldsPrivacy[efbc:FieldIdentifierCode/text()='awa-cri-ord']/efbc:ReasonDescription</span></code>
        </td>
        <td class="mapping">

Get the `withheldInformationItem` object created for BT-195(BT-733)-LotsGroup and `ancestor::cac:ProcurementProjectLot[cbc:ID schemeName="LotsGroup"]` and map to its `.rationale`.

```xml
<efac:FieldsPrivacy>
  <efbc:ReasonDescription languageID="ENG">Information delayed publication because of ...</efbc:ReasonDescription>
</efac:FieldsPrivacy>
```

```json
{
  "withheldInformation": [
    {
      "rationale": "Information delayed publication because of ..."
    }
  ]
}
```

</td>
      </tr>
      <tr id="BT-196(BT-734)-Lot">
        <td class="field break-all">
            <p><b>BT-196(BT-734)-Lot</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/withheld-publication.html#lotsGroupOfLotsLevelSection"></a><br>Unpublished Justification Description</p><p><i>BT-196:</i> The justification for not immediately publishing a field and for the choice of a later date at which it can be published.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='Lot']/cac:TenderingTerms/cac:AwardingTerms/cac:AwardingCriterion/cac:SubordinateAwardingCriterion/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:FieldsPrivacy[efbc:FieldIdentifierCode/text()='awa-cri-nam']/efbc:ReasonDescription</span></code>
        </td>
        <td class="mapping">

Get the `withheldInformationItem` object created for BT-195(BT-734)-Lot and `ancestor::cac:ProcurementProjectLot[cbc:ID schemeName="Lot"]` and map to its `.rationale`.

```xml
<efac:FieldsPrivacy>
  <efbc:ReasonDescription languageID="ENG">Information delayed publication because of ...</efbc:ReasonDescription>
</efac:FieldsPrivacy>
```

```json
{
  "withheldInformation": [
    {
      "rationale": "Information delayed publication because of ..."
    }
  ]
}
```

</td>
      </tr>
      <tr id="BT-196(BT-734)-LotsGroup">
        <td class="field break-all">
            <p><b>BT-196(BT-734)-LotsGroup</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/withheld-publication.html#lotsGroupOfLotsLevelSection"></a><br>Unpublished Justification Description</p><p><i>BT-196:</i> The justification for not immediately publishing a field and for the choice of a later date at which it can be published.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='LotsGroup']/cac:TenderingTerms/cac:AwardingTerms/cac:AwardingCriterion/cac:SubordinateAwardingCriterion/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:FieldsPrivacy[efbc:FieldIdentifierCode/text()='awa-cri-nam']/efbc:ReasonDescription</span></code>
        </td>
        <td class="mapping">

Get the `withheldInformationItem` object created for BT-195(BT-734)-LotsGroup and `ancestor::cac:ProcurementProjectLot[cbc:ID schemeName="LotsGroup"]` and map to its `.rationale`.

```xml
<efac:FieldsPrivacy>
  <efbc:ReasonDescription languageID="ENG">Information delayed publication because of ...</efbc:ReasonDescription>
</efac:FieldsPrivacy>
```

```json
{
  "withheldInformation": [
    {
      "rationale": "Information delayed publication because of ..."
    }
  ]
}
```

</td>
      </tr>
      <tr id="BT-196(BT-759)-LotResult">
        <td class="field break-all">
            <p><b>BT-196(BT-759)-LotResult</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/withheld-publication.html#lotResultLevelSection"></a><br>Unpublished Justification Description</p><p><i>BT-196:</i> The justification for not immediately publishing a field and for the choice of a later date at which it can be published.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:NoticeResult/efac:LotResult/efac:ReceivedSubmissionsStatistics/efac:FieldsPrivacy[efbc:FieldIdentifierCode/text()='rec-sub-cou']/efbc:ReasonDescription</span></code>
        </td>
        <td class="mapping">

Get the `withheldInformationItem` object created for BT-195(BT-759)-LotResult and `ancestor::efac:LotResult` and map to its `.rationale`.

```xml
<efac:FieldsPrivacy>
  <efbc:ReasonDescription languageID="ENG">Information delayed publication because of ...</efbc:ReasonDescription>
</efac:FieldsPrivacy>
```

```json
{
  "withheldInformation": [
    {
      "rationale": "Information delayed publication because of ..."
    }
  ]
}
```

</td>
      </tr>
      <tr id="BT-196(BT-760)-LotResult">
        <td class="field break-all">
            <p><b>BT-196(BT-760)-LotResult</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/withheld-publication.html#lotResultLevelSection"></a><br>Unpublished Justification Description</p><p><i>BT-196:</i> The justification for not immediately publishing a field and for the choice of a later date at which it can be published.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:NoticeResult/efac:LotResult/efac:ReceivedSubmissionsStatistics/efac:FieldsPrivacy[efbc:FieldIdentifierCode/text()='rec-sub-typ']/efbc:ReasonDescription</span></code>
        </td>
        <td class="mapping">

Get the `withheldInformationItem` object created for BT-195(BT-760)-LotResult and `ancestor::efac:LotResult` and map to its `.rationale`.

```xml
<efac:FieldsPrivacy>
  <efbc:ReasonDescription languageID="ENG">Information delayed publication because of ...</efbc:ReasonDescription>
</efac:FieldsPrivacy>
```

```json
{
  "withheldInformation": [
    {
      "rationale": "Information delayed publication because of ..."
    }
  ]
}
```

</td>
      </tr>
      <tr id="BT-196(BT-773)-Tender">
        <td class="field break-all">
            <p><b>BT-196(BT-773)-Tender</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/withheld-publication.html#lotTenderLevelSection"></a><br>Unpublished Justification Description</p><p><i>BT-196:</i> The justification for not immediately publishing a field and for the choice of a later date at which it can be published.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:NoticeResult/efac:LotTender/efac:SubcontractingTerm/efac:FieldsPrivacy[efbc:FieldIdentifierCode/text()='sub-con']/efbc:ReasonDescription</span></code>
        </td>
        <td class="mapping">

Get the `withheldInformationItem` object created for BT-195(BT-773)-Tender and `ancestor::efac:LotTender` and map to its `.rationale`.

```xml
<efac:FieldsPrivacy>
  <efbc:ReasonDescription languageID="ENG">Information delayed publication because of ...</efbc:ReasonDescription>
</efac:FieldsPrivacy>
```

```json
{
  "withheldInformation": [
    {
      "rationale": "Information delayed publication because of ..."
    }
  ]
}
```

</td>
      </tr>
      <tr id="BT-196(BT-88)-Procedure">
        <td class="field break-all">
            <p><b>BT-196(BT-88)-Procedure</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/withheld-publication.html#procedureLevelSection"></a><br>Unpublished Justification Description</p><p><i>BT-196:</i> The justification for not immediately publishing a field and for the choice of a later date at which it can be published.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:TenderingProcess/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:FieldsPrivacy[efbc:FieldIdentifierCode/text()='pro-fea']/efbc:ReasonDescription</span></code>
        </td>
        <td class="mapping">

Get the `withheldInformationItem` object created for BT-195(BT-88)-Procedure and map to its `.rationale`.

```xml
<efac:FieldsPrivacy>
  <efbc:ReasonDescription languageID="ENG">Information delayed publication because of ...</efbc:ReasonDescription>
</efac:FieldsPrivacy>
```

```json
{
  "withheldInformation": [
    {
      "rationale": "Information delayed publication because of ..."
    }
  ]
}
```

</td>
      </tr>
      <tr id="BT-197(BT-09)-Procedure">
        <td class="field break-all">
            <p><b>BT-197(BT-09)-Procedure</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/withheld-publication.html#procedureLevelSection"></a><br>Unpublished Justification Code</p><p><i>BT-197:</i> The justification for not immediately publishing a field.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:TenderingTerms/cac:ProcurementLegislationDocumentReference[cbc:ID/text()='CrossBorderLaw']/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:FieldsPrivacy[efbc:FieldIdentifierCode/text()='cro-bor-law']/cbc:ReasonCode</span></code>
        </td>
        <td class="mapping">

Get the `withheldInformationItem` object created for BT-195(BT-09)-Procedure. Add a `.rationaleClassification` object to it and map the value of the `cbc:ReasonCode` to `.id` and the `cbc:ReasonCode[@listName]` to `.scheme`. Look up the code in the <a href="https://op.europa.eu/en/web/eu-vocabularies/concept-scheme/-/resource?uri=http://publications.europa.eu/resource/authority/non-publication-justification">authority table</a>, map its label to `.description` and its URI to `.uri`.

```xml
<efac:FieldsPrivacy>
  <cbc:ReasonCode listName="non-publication-justification">oth-int</cbc:ReasonCode>
</efac:FieldsPrivacy>
```

```json
{
  "withheldInformation": [
    {
      "rationaleClassification": {
        "scheme": "non-publication-justification",
        "id": "oth-int",
        "description": "Other public interest",
        "uri": "http://publications.europa.eu/resource/authority/non-publication-justification/oth-int"
      }
    }
  ]
}
```

</td>
      </tr>
      <tr id="BT-197(BT-105)-Procedure">
        <td class="field break-all">
            <p><b>BT-197(BT-105)-Procedure</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/withheld-publication.html#procedureLevelSection"></a><br>Unpublished Justification Code</p><p><i>BT-197:</i> The justification for not immediately publishing a field.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:TenderingProcess/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:FieldsPrivacy[efbc:FieldIdentifierCode/text()='pro-typ']/cbc:ReasonCode</span></code>
        </td>
        <td class="mapping">

Get the `withheldInformationItem` object created for BT-195(BT-105)-Procedure. Add a `.rationaleClassification` object to it and map the value of the `cbc:ReasonCode` to `.id` and the `cbc:ReasonCode[@listName]` to `.scheme`. Look up the code in the <a href="https://op.europa.eu/en/web/eu-vocabularies/concept-scheme/-/resource?uri=http://publications.europa.eu/resource/authority/non-publication-justification">authority table</a>, map its label to `.description` and its URI to `.uri`.

```xml
<efac:FieldsPrivacy>
  <cbc:ReasonCode listName="non-publication-justification">oth-int</cbc:ReasonCode>
</efac:FieldsPrivacy>
```

```json
{
  "withheldInformation": [
    {
      "rationaleClassification": {
        "scheme": "non-publication-justification",
        "id": "oth-int",
        "description": "Other public interest",
        "uri": "http://publications.europa.eu/resource/authority/non-publication-justification/oth-int"
      }
    }
  ]
}
```

</td>
      </tr>
      <tr id="BT-197(BT-106)-Procedure">
        <td class="field break-all">
            <p><b>BT-197(BT-106)-Procedure</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/withheld-publication.html#procedureLevelSection"></a><br>Unpublished Justification Code</p><p><i>BT-197:</i> The justification for not immediately publishing a field.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:TenderingProcess/cac:ProcessJustification[cbc:ProcessReasonCode/@listName='accelerated-procedure']/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:FieldsPrivacy[efbc:FieldIdentifierCode/text()='pro-acc']/cbc:ReasonCode</span></code>
        </td>
        <td class="mapping">

Get the `withheldInformationItem` object created for BT-195(BT-106)-Procedure. Add a `.rationaleClassification` object to it and map the value of the `cbc:ReasonCode` to `.id` and the `cbc:ReasonCode[@listName]` to `.scheme`. Look up the code in the <a href="https://op.europa.eu/en/web/eu-vocabularies/concept-scheme/-/resource?uri=http://publications.europa.eu/resource/authority/non-publication-justification">authority table</a>, map its label to `.description` and its URI to `.uri`.

```xml
<efac:FieldsPrivacy>
  <cbc:ReasonCode listName="non-publication-justification">oth-int</cbc:ReasonCode>
</efac:FieldsPrivacy>
```

```json
{
  "withheldInformation": [
    {
      "rationaleClassification": {
        "scheme": "non-publication-justification",
        "id": "oth-int",
        "description": "Other public interest",
        "uri": "http://publications.europa.eu/resource/authority/non-publication-justification/oth-int"
      }
    }
  ]
}
```

</td>
      </tr>
      <tr id="BT-197(BT-1118)-NoticeResult">
        <td class="field break-all">
            <p><b>BT-197(BT-1118)-NoticeResult</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/withheld-publication.html#_notice_result_level"></a><br>Unpublished Justification Code</p><p><i>BT-197:</i> The justification for not immediately publishing a field.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:NoticeResult/efac:FieldsPrivacy[efbc:FieldIdentifierCode/text()='not-app-val']/cbc:ReasonCode</span></code>
        </td>
        <td class="mapping">

Discard.

```xml
<efac:FieldsPrivacy>
  <cbc:ReasonCode listName="non-publication-justification">oth-int</cbc:ReasonCode>
</efac:FieldsPrivacy>
```



</td>
      </tr>
      <tr id="BT-197(BT-118)-NoticeResult">
        <td class="field break-all">
            <p><b>BT-197(BT-118)-NoticeResult</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/withheld-publication.html#_notice_result_level"></a><br>Unpublished Justification Code</p><p><i>BT-197:</i> The justification for not immediately publishing a field.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:NoticeResult/efac:FieldsPrivacy[efbc:FieldIdentifierCode/text()='not-max-val']/cbc:ReasonCode</span></code>
        </td>
        <td class="mapping">

Discard.

```xml
<efac:FieldsPrivacy>
  <cbc:ReasonCode listName="non-publication-justification">oth-int</cbc:ReasonCode>
</efac:FieldsPrivacy>
```



</td>
      </tr>
      <tr id="BT-197(BT-1252)-Procedure">
        <td class="field break-all">
            <p><b>BT-197(BT-1252)-Procedure</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/withheld-publication.html#procedureLevelSection"></a><br>Unpublished Justification Code</p><p><i>BT-197:</i> The justification for not immediately publishing a field.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:TenderingProcess/cac:ProcessJustification[cbc:ProcessReasonCode/@listName='direct-award-justification']/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:FieldsPrivacy[efbc:FieldIdentifierCode/text()='dir-awa-pre']/cbc:ReasonCode</span></code>
        </td>
        <td class="mapping">

Get the `withheldInformationItem` object created for BT-195(BT-1252)-Procedure. Add a `.rationaleClassification` object to it and map the value of the `cbc:ReasonCode` to `.id` and the `cbc:ReasonCode[@listName]` to `.scheme`. Look up the code in the <a href="https://op.europa.eu/en/web/eu-vocabularies/concept-scheme/-/resource?uri=http://publications.europa.eu/resource/authority/non-publication-justification">authority table</a>, map its label to `.description` and its URI to `.uri`.

```xml
<efac:FieldsPrivacy>
  <cbc:ReasonCode listName="non-publication-justification">oth-int</cbc:ReasonCode>
</efac:FieldsPrivacy>
```

```json
{
  "withheldInformation": [
    {
      "rationaleClassification": {
        "scheme": "non-publication-justification",
        "id": "oth-int",
        "description": "Other public interest",
        "uri": "http://publications.europa.eu/resource/authority/non-publication-justification/oth-int"
      }
    }
  ]
}
```

</td>
      </tr>
      <tr id="BT-197(BT-135)-Procedure">
        <td class="field break-all">
            <p><b>BT-197(BT-135)-Procedure</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/withheld-publication.html#procedureLevelSection"></a><br>Unpublished Justification Code</p><p><i>BT-197:</i> The justification for not immediately publishing a field.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:TenderingProcess/cac:ProcessJustification[cbc:ProcessReasonCode/@listName='direct-award-justification']/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:FieldsPrivacy[efbc:FieldIdentifierCode/text()='dir-awa-tex']/cbc:ReasonCode</span></code>
        </td>
        <td class="mapping">

Get the `withheldInformationItem` object created for BT-195(BT-1252)-Procedure. Add a `.rationaleClassification` object to it and map the value of the `cbc:ReasonCode` to `.id` and the `cbc:ReasonCode[@listName]` to `.scheme`. Look up the code in the <a href="https://op.europa.eu/en/web/eu-vocabularies/concept-scheme/-/resource?uri=http://publications.europa.eu/resource/authority/non-publication-justification">authority table</a>, map its label to `.description` and its URI to `.uri`.

```xml
<efac:FieldsPrivacy>
  <cbc:ReasonCode listName="non-publication-justification">oth-int</cbc:ReasonCode>
</efac:FieldsPrivacy>
```

```json
{
  "withheldInformation": [
    {
      "rationaleClassification": {
        "scheme": "non-publication-justification",
        "id": "oth-int",
        "description": "Other public interest",
        "uri": "http://publications.europa.eu/resource/authority/non-publication-justification/oth-int"
      }
    }
  ]
}
```

</td>
      </tr>
      <tr id="BT-197(BT-1351)-Procedure">
        <td class="field break-all">
            <p><b>BT-197(BT-1351)-Procedure</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/withheld-publication.html#procedureLevelSection"></a><br>Unpublished Justification Code</p><p><i>BT-197:</i> The justification for not immediately publishing a field.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:TenderingProcess/cac:ProcessJustification[cbc:ProcessReasonCode/@listName='accelerated-procedure']/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:FieldsPrivacy[efbc:FieldIdentifierCode/text()='pro-acc-jus']/cbc:ReasonCode</span></code>
        </td>
        <td class="mapping">

Get the `withheldInformationItem` object created for BT-195(BT-1351)-Procedure. Add a `.rationaleClassification` object to it and map the value of the `cbc:ReasonCode` to `.id` and the `cbc:ReasonCode[@listName]` to `.scheme`. Look up the code in the <a href="https://op.europa.eu/en/web/eu-vocabularies/concept-scheme/-/resource?uri=http://publications.europa.eu/resource/authority/non-publication-justification">authority table</a>, map its label to `.description` and its URI to `.uri`.

```xml
<efac:FieldsPrivacy>
  <cbc:ReasonCode listName="non-publication-justification">oth-int</cbc:ReasonCode>
</efac:FieldsPrivacy>
```

```json
{
  "withheldInformation": [
    {
      "rationaleClassification": {
        "scheme": "non-publication-justification",
        "id": "oth-int",
        "description": "Other public interest",
        "uri": "http://publications.europa.eu/resource/authority/non-publication-justification/oth-int"
      }
    }
  ]
}
```

</td>
      </tr>
      <tr id="BT-197(BT-136)-Procedure">
        <td class="field break-all">
            <p><b>BT-197(BT-136)-Procedure</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/withheld-publication.html#procedureLevelSection"></a><br>Unpublished Justification Code</p><p><i>BT-197:</i> The justification for not immediately publishing a field.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:TenderingProcess/cac:ProcessJustification[cbc:ProcessReasonCode/@listName='direct-award-justification']/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:FieldsPrivacy[efbc:FieldIdentifierCode/text()='dir-awa-jus']/cbc:ReasonCode</span></code>
        </td>
        <td class="mapping">

Get the `withheldInformationItem` object created for BT-195(BT-136)-Procedure. Add a `.rationaleClassification` object to it and map the value of the `cbc:ReasonCode` to `.id` and the `cbc:ReasonCode[@listName]` to `.scheme`. Look up the code in the <a href="https://op.europa.eu/en/web/eu-vocabularies/concept-scheme/-/resource?uri=http://publications.europa.eu/resource/authority/non-publication-justification">authority table</a>, map its label to `.description` and its URI to `.uri`.

```xml
<efac:FieldsPrivacy>
  <cbc:ReasonCode listName="non-publication-justification">oth-int</cbc:ReasonCode>
</efac:FieldsPrivacy>
```

```json
{
  "withheldInformation": [
    {
      "rationaleClassification": {
        "scheme": "non-publication-justification",
        "id": "oth-int",
        "description": "Other public interest",
        "uri": "http://publications.europa.eu/resource/authority/non-publication-justification/oth-int"
      }
    }
  ]
}
```

</td>
      </tr>
      <tr id="BT-197(BT-142)-LotResult">
        <td class="field break-all">
            <p><b>BT-197(BT-142)-LotResult</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/withheld-publication.html#lotResultLevelSection"></a><br>Unpublished Justification Code</p><p><i>BT-197:</i> The justification for not immediately publishing a field.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:NoticeResult/efac:LotResult/efac:FieldsPrivacy[efbc:FieldIdentifierCode/text()='win-cho']/cbc:ReasonCode</span></code>
        </td>
        <td class="mapping">

Get the `withheldInformationItem` object created for BT-195(BT-142)-LotResult and `ancestor::efac:LotResult`. Add a `.rationaleClassification` object to it and map the value of the `cbc:ReasonCode` to `.id` and the `cbc:ReasonCode[@listName]` to `.scheme`. Look up the code in the <a href="https://op.europa.eu/en/web/eu-vocabularies/concept-scheme/-/resource?uri=http://publications.europa.eu/resource/authority/non-publication-justification">authority table</a>, map its label to `.description` and its URI to `.uri`.

```xml
<efac:FieldsPrivacy>
  <cbc:ReasonCode listName="non-publication-justification">oth-int</cbc:ReasonCode>
</efac:FieldsPrivacy>
```

```json
{
  "withheldInformation": [
    {
      "rationaleClassification": {
        "scheme": "non-publication-justification",
        "id": "oth-int",
        "description": "Other public interest",
        "uri": "http://publications.europa.eu/resource/authority/non-publication-justification/oth-int"
      }
    }
  ]
}
```

</td>
      </tr>
      <tr id="BT-197(BT-144)-LotResult">
        <td class="field break-all">
            <p><b>BT-197(BT-144)-LotResult</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/withheld-publication.html#lotResultLevelSection"></a><br>Unpublished Justification Code</p><p><i>BT-197:</i> The justification for not immediately publishing a field.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:NoticeResult/efac:LotResult/efac:DecisionReason/efac:FieldsPrivacy[efbc:FieldIdentifierCode/text()='no-awa-rea']/cbc:ReasonCode</span></code>
        </td>
        <td class="mapping">

Get the `withheldInformationItem` object created for BT-195(BT-144)-LotResult and `ancestor::efac:LotResult`. Add a `.rationaleClassification` object to it and map the value of the `cbc:ReasonCode` to `.id` and the `cbc:ReasonCode[@listName]` to `.scheme`. Look up the code in the <a href="https://op.europa.eu/en/web/eu-vocabularies/concept-scheme/-/resource?uri=http://publications.europa.eu/resource/authority/non-publication-justification">authority table</a>, map its label to `.description` and its URI to `.uri`.

```xml
<efac:FieldsPrivacy>
  <cbc:ReasonCode listName="non-publication-justification">oth-int</cbc:ReasonCode>
</efac:FieldsPrivacy>
```

```json
{
  "withheldInformation": [
    {
      "rationaleClassification": {
        "scheme": "non-publication-justification",
        "id": "oth-int",
        "description": "Other public interest",
        "uri": "http://publications.europa.eu/resource/authority/non-publication-justification/oth-int"
      }
    }
  ]
}
```

</td>
      </tr>
      <tr id="BT-197(BT-156)-NoticeResult">
        <td class="field break-all">
            <p><b>BT-197(BT-156)-NoticeResult</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/withheld-publication.html#_notice_result_level"></a><br>Unpublished Justification Code</p><p><i>BT-197:</i> The justification for not immediately publishing a field.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:NoticeResult/efac:GroupFramework/efac:FieldsPrivacy[efbc:FieldIdentifierCode/text()='gro-max-val']/cbc:ReasonCode</span></code>
        </td>
        <td class="mapping">

Discard.

```xml
<efac:FieldsPrivacy>
  <cbc:ReasonCode listName="non-publication-justification">oth-int</cbc:ReasonCode>
</efac:FieldsPrivacy>
```



</td>
      </tr>
      <tr id="BT-197(BT-1561)-NoticeResult">
        <td class="field break-all">
            <p><b>BT-197(BT-1561)-NoticeResult</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/withheld-publication.html#_notice_result_level"></a><br>Unpublished Justification Code</p><p><i>BT-197:</i> The justification for not immediately publishing a field.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:NoticeResult/efac:GroupFramework/efac:FieldsPrivacy[efbc:FieldIdentifierCode/text()='not-ree-val']/cbc:ReasonCode</span></code>
        </td>
        <td class="mapping">

Discard.

```xml
<efac:FieldsPrivacy>
  <cbc:ReasonCode listName="non-publication-justification">oth-int</cbc:ReasonCode>
</efac:FieldsPrivacy>
```



</td>
      </tr>
      <tr id="BT-197(BT-160)-Tender">
        <td class="field break-all">
            <p><b>BT-197(BT-160)-Tender</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/withheld-publication.html#lotTenderLevelSection"></a><br>Unpublished Justification Code</p><p><i>BT-197:</i> The justification for not immediately publishing a field.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:NoticeResult/efac:LotTender/efac:ConcessionRevenue/efac:FieldsPrivacy[efbc:FieldIdentifierCode/text()='con-rev-buy']/cbc:ReasonCode</span></code>
        </td>
        <td class="mapping">

Get the `withheldInformationItem` object created for BT-195(BT-160)-Tender and `ancestor::efac:LotTender`. Add a `.rationaleClassification` object to it and map the value of the `cbc:ReasonCode` to `.id` and the `cbc:ReasonCode[@listName]` to `.scheme`. Look up the code in the <a href="https://op.europa.eu/en/web/eu-vocabularies/concept-scheme/-/resource?uri=http://publications.europa.eu/resource/authority/non-publication-justification">authority table</a>, map its label to `.description` and its URI to `.uri`.

```xml
<efac:FieldsPrivacy>
  <cbc:ReasonCode listName="non-publication-justification">oth-int</cbc:ReasonCode>
</efac:FieldsPrivacy>
```

```json
{
  "withheldInformation": [
    {
      "rationaleClassification": {
        "scheme": "non-publication-justification",
        "id": "oth-int",
        "description": "Other public interest",
        "uri": "http://publications.europa.eu/resource/authority/non-publication-justification/oth-int"
      }
    }
  ]
}
```

</td>
      </tr>
      <tr id="BT-197(BT-161)-NoticeResult">
        <td class="field break-all">
            <p><b>BT-197(BT-161)-NoticeResult</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/withheld-publication.html#_notice_result_level"></a><br>Unpublished Justification Code</p><p><i>BT-197:</i> The justification for not immediately publishing a field.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:NoticeResult/efac:FieldsPrivacy[efbc:FieldIdentifierCode/text()='not-val']/cbc:ReasonCode</span></code>
        </td>
        <td class="mapping">

Discard.

```xml
<efac:FieldsPrivacy>
  <cbc:ReasonCode listName="non-publication-justification">oth-int</cbc:ReasonCode>
</efac:FieldsPrivacy>
```



</td>
      </tr>
      <tr id="BT-197(BT-162)-Tender">
        <td class="field break-all">
            <p><b>BT-197(BT-162)-Tender</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/withheld-publication.html#lotTenderLevelSection"></a><br>Unpublished Justification Code</p><p><i>BT-197:</i> The justification for not immediately publishing a field.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:NoticeResult/efac:LotTender/efac:ConcessionRevenue/efac:FieldsPrivacy[efbc:FieldIdentifierCode/text()='con-rev-use']/cbc:ReasonCode</span></code>
        </td>
        <td class="mapping">

Get the `withheldInformationItem` object created for BT-195(BT-162)-Tender and `ancestor::efac:LotTender`. Add a `.rationaleClassification` object to it and map the value of the `cbc:ReasonCode` to `.id` and the `cbc:ReasonCode[@listName]` to `.scheme`. Look up the code in the <a href="https://op.europa.eu/en/web/eu-vocabularies/concept-scheme/-/resource?uri=http://publications.europa.eu/resource/authority/non-publication-justification">authority table</a>, map its label to `.description` and its URI to `.uri`.

```xml
<efac:FieldsPrivacy>
  <cbc:ReasonCode listName="non-publication-justification">oth-int</cbc:ReasonCode>
</efac:FieldsPrivacy>
```

```json
{
  "withheldInformation": [
    {
      "rationaleClassification": {
        "scheme": "non-publication-justification",
        "id": "oth-int",
        "description": "Other public interest",
        "uri": "http://publications.europa.eu/resource/authority/non-publication-justification/oth-int"
      }
    }
  ]
}
```

</td>
      </tr>
      <tr id="BT-197(BT-163)-Tender">
        <td class="field break-all">
            <p><b>BT-197(BT-163)-Tender</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/withheld-publication.html#lotTenderLevelSection"></a><br>Unpublished Justification Code</p><p><i>BT-197:</i> The justification for not immediately publishing a field.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:NoticeResult/efac:LotTender/efac:ConcessionRevenue/efac:FieldsPrivacy[efbc:FieldIdentifierCode/text()='val-con-des']/cbc:ReasonCode</span></code>
        </td>
        <td class="mapping">

Get the `withheldInformationItem` object created for BT-195(BT-163)-Tender and `ancestor::efac:LotTender`. Add a `.rationaleClassification` object to it and map the value of the `cbc:ReasonCode` to `.id` and the `cbc:ReasonCode[@listName]` to `.scheme`. Look up the code in the <a href="https://op.europa.eu/en/web/eu-vocabularies/concept-scheme/-/resource?uri=http://publications.europa.eu/resource/authority/non-publication-justification">authority table</a>, map its label to `.description` and its URI to `.uri`.

```xml
<efac:FieldsPrivacy>
  <cbc:ReasonCode listName="non-publication-justification">oth-int</cbc:ReasonCode>
</efac:FieldsPrivacy>
```

```json
{
  "withheldInformation": [
    {
      "rationaleClassification": {
        "scheme": "non-publication-justification",
        "id": "oth-int",
        "description": "Other public interest",
        "uri": "http://publications.europa.eu/resource/authority/non-publication-justification/oth-int"
      }
    }
  ]
}
```

</td>
      </tr>
      <tr id="BT-197(BT-171)-Tender">
        <td class="field break-all">
            <p><b>BT-197(BT-171)-Tender</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/withheld-publication.html#lotTenderLevelSection"></a><br>Unpublished Justification Code</p><p><i>BT-197:</i> The justification for not immediately publishing a field.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:NoticeResult/efac:LotTender/efac:FieldsPrivacy[efbc:FieldIdentifierCode/text()='ten-ran']/cbc:ReasonCode</span></code>
        </td>
        <td class="mapping">

Get the `withheldInformationItem` object created for BT-195(BT-171)-Tender and `ancestor::efac:LotTender`. Add a `.rationaleClassification` object to it and map the value of the `cbc:ReasonCode` to `.id` and the `cbc:ReasonCode[@listName]` to `.scheme`. Look up the code in the <a href="https://op.europa.eu/en/web/eu-vocabularies/concept-scheme/-/resource?uri=http://publications.europa.eu/resource/authority/non-publication-justification">authority table</a>, map its label to `.description` and its URI to `.uri`.

```xml
<efac:FieldsPrivacy>
  <cbc:ReasonCode listName="non-publication-justification">oth-int</cbc:ReasonCode>
</efac:FieldsPrivacy>
```

```json
{
  "withheldInformation": [
    {
      "rationaleClassification": {
        "scheme": "non-publication-justification",
        "id": "oth-int",
        "description": "Other public interest",
        "uri": "http://publications.europa.eu/resource/authority/non-publication-justification/oth-int"
      }
    }
  ]
}
```

</td>
      </tr>
      <tr id="BT-197(BT-191)-Tender">
        <td class="field break-all">
            <p><b>BT-197(BT-191)-Tender</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/withheld-publication.html#lotTenderLevelSection"></a><br>Unpublished Justification Code</p><p><i>BT-197:</i> The justification for not immediately publishing a field.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:NoticeResult/efac:LotTender/efac:Origin/efac:FieldsPrivacy[efbc:FieldIdentifierCode/text()='cou-ori']/cbc:ReasonCode</span></code>
        </td>
        <td class="mapping">

Get the `withheldInformationItem` object created for BT-195(BT-191)-Tender and `ancestor::efac:LotTender`. Add a `.rationaleClassification` object to it and map the value of the `cbc:ReasonCode` to `.id` and the `cbc:ReasonCode[@listName]` to `.scheme`. Look up the code in the <a href="https://op.europa.eu/en/web/eu-vocabularies/concept-scheme/-/resource?uri=http://publications.europa.eu/resource/authority/non-publication-justification">authority table</a>, map its label to `.description` and its URI to `.uri`.

```xml
<efac:FieldsPrivacy>
  <cbc:ReasonCode listName="non-publication-justification">oth-int</cbc:ReasonCode>
</efac:FieldsPrivacy>
```

```json
{
  "withheldInformation": [
    {
      "rationaleClassification": {
        "scheme": "non-publication-justification",
        "id": "oth-int",
        "description": "Other public interest",
        "uri": "http://publications.europa.eu/resource/authority/non-publication-justification/oth-int"
      }
    }
  ]
}
```

</td>
      </tr>
      <tr id="BT-197(BT-193)-Tender">
        <td class="field break-all">
            <p><b>BT-197(BT-193)-Tender</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/withheld-publication.html#lotTenderLevelSection"></a><br>Unpublished Justification Code</p><p><i>BT-197:</i> The justification for not immediately publishing a field.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:NoticeResult/efac:LotTender/efac:FieldsPrivacy[efbc:FieldIdentifierCode/text()='win-ten-var']/cbc:ReasonCode</span></code>
        </td>
        <td class="mapping">

Get the `withheldInformationItem` object created for BT-195(BT-193)-Tender and `ancestor::efac:LotTender`. Add a `.rationaleClassification` object to it and map the value of the `cbc:ReasonCode` to `.id` and the `cbc:ReasonCode[@listName]` to `.scheme`. Look up the code in the <a href="https://op.europa.eu/en/web/eu-vocabularies/concept-scheme/-/resource?uri=http://publications.europa.eu/resource/authority/non-publication-justification">authority table</a>, map its label to `.description` and its URI to `.uri`.

```xml
<efac:FieldsPrivacy>
  <cbc:ReasonCode listName="non-publication-justification">oth-int</cbc:ReasonCode>
</efac:FieldsPrivacy>
```

```json
{
  "withheldInformation": [
    {
      "rationaleClassification": {
        "scheme": "non-publication-justification",
        "id": "oth-int",
        "description": "Other public interest",
        "uri": "http://publications.europa.eu/resource/authority/non-publication-justification/oth-int"
      }
    }
  ]
}
```

</td>
      </tr>
      <tr id="BT-197(BT-539)-Lot">
        <td class="field break-all">
            <p><b>BT-197(BT-539)-Lot</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/withheld-publication.html#lotsGroupOfLotsLevelSection"></a><br>Unpublished Justification Code</p><p><i>BT-197:</i> The justification for not immediately publishing a field.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='Lot']/cac:TenderingTerms/cac:AwardingTerms/cac:AwardingCriterion/cac:SubordinateAwardingCriterion/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:FieldsPrivacy[efbc:FieldIdentifierCode/text()='awa-cri-typ']/cbc:ReasonCode</span></code>
        </td>
        <td class="mapping">

Get the `withheldInformationItem` object created for BT-195(BT-539)-Lot and `ancestor::cac:ProcurementProjectLot[cbc:ID schemeName="Lot"]`. Add a `.rationaleClassification` object to it and map the value of the `cbc:ReasonCode` to `.id` and the `cbc:ReasonCode[@listName]` to `.scheme`. Look up the code in the <a href="https://op.europa.eu/en/web/eu-vocabularies/concept-scheme/-/resource?uri=http://publications.europa.eu/resource/authority/non-publication-justification">authority table</a>, map its label to `.description` and its URI to `.uri`.

```xml
<efac:FieldsPrivacy>
  <cbc:ReasonCode listName="non-publication-justification">oth-int</cbc:ReasonCode>
</efac:FieldsPrivacy>
```

```json
{
  "withheldInformation": [
    {
      "rationaleClassification": {
        "scheme": "non-publication-justification",
        "id": "oth-int",
        "description": "Other public interest",
        "uri": "http://publications.europa.eu/resource/authority/non-publication-justification/oth-int"
      }
    }
  ]
}
```

</td>
      </tr>
      <tr id="BT-197(BT-539)-LotsGroup">
        <td class="field break-all">
            <p><b>BT-197(BT-539)-LotsGroup</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/withheld-publication.html#lotsGroupOfLotsLevelSection"></a><br>Unpublished Justification Code</p><p><i>BT-197:</i> The justification for not immediately publishing a field.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='LotsGroup']/cac:TenderingTerms/cac:AwardingTerms/cac:AwardingCriterion/cac:SubordinateAwardingCriterion/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:FieldsPrivacy[efbc:FieldIdentifierCode/text()='awa-cri-typ']/cbc:ReasonCode</span></code>
        </td>
        <td class="mapping">

Get the `withheldInformationItem` object created for BT-195(BT-539)-LotsGroup and `ancestor::cac:ProcurementProjectLot[cbc:ID schemeName="LotsGroup"]`. Add a `.rationaleClassification` object to it and map the value of the `cbc:ReasonCode` to `.id` and the `cbc:ReasonCode[@listName]` to `.scheme`. Look up the code in the <a href="https://op.europa.eu/en/web/eu-vocabularies/concept-scheme/-/resource?uri=http://publications.europa.eu/resource/authority/non-publication-justification">authority table</a>, map its label to `.description` and its URI to `.uri`.

```xml
<efac:FieldsPrivacy>
  <cbc:ReasonCode listName="non-publication-justification">oth-int</cbc:ReasonCode>
</efac:FieldsPrivacy>
```

```json
{
  "withheldInformation": [
    {
      "rationaleClassification": {
        "scheme": "non-publication-justification",
        "id": "oth-int",
        "description": "Other public interest",
        "uri": "http://publications.europa.eu/resource/authority/non-publication-justification/oth-int"
      }
    }
  ]
}
```

</td>
      </tr>
      <tr id="BT-197(BT-540)-Lot">
        <td class="field break-all">
            <p><b>BT-197(BT-540)-Lot</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/withheld-publication.html#lotsGroupOfLotsLevelSection"></a><br>Unpublished Justification Code</p><p><i>BT-197:</i> The justification for not immediately publishing a field.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='Lot']/cac:TenderingTerms/cac:AwardingTerms/cac:AwardingCriterion/cac:SubordinateAwardingCriterion/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:FieldsPrivacy[efbc:FieldIdentifierCode/text()='awa-cri-des']/cbc:ReasonCode</span></code>
        </td>
        <td class="mapping">

Get the `withheldInformationItem` object created for BT-195(BT-540)-Lot and `ancestor::cac:ProcurementProjectLot[cbc:ID schemeName="Lot"]`. Add a `.rationaleClassification` object to it and map the value of the `cbc:ReasonCode` to `.id` and the `cbc:ReasonCode[@listName]` to `.scheme`. Look up the code in the <a href="https://op.europa.eu/en/web/eu-vocabularies/concept-scheme/-/resource?uri=http://publications.europa.eu/resource/authority/non-publication-justification">authority table</a>, map its label to `.description` and its URI to `.uri`.

```xml
<efac:FieldsPrivacy>
  <cbc:ReasonCode listName="non-publication-justification">oth-int</cbc:ReasonCode>
</efac:FieldsPrivacy>
```

```json
{
  "withheldInformation": [
    {
      "rationaleClassification": {
        "scheme": "non-publication-justification",
        "id": "oth-int",
        "description": "Other public interest",
        "uri": "http://publications.europa.eu/resource/authority/non-publication-justification/oth-int"
      }
    }
  ]
}
```

</td>
      </tr>
      <tr id="BT-197(BT-540)-LotsGroup">
        <td class="field break-all">
            <p><b>BT-197(BT-540)-LotsGroup</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/withheld-publication.html#lotsGroupOfLotsLevelSection"></a><br>Unpublished Justification Code</p><p><i>BT-197:</i> The justification for not immediately publishing a field.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='LotsGroup']/cac:TenderingTerms/cac:AwardingTerms/cac:AwardingCriterion/cac:SubordinateAwardingCriterion/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:FieldsPrivacy[efbc:FieldIdentifierCode/text()='awa-cri-des']/cbc:ReasonCode</span></code>
        </td>
        <td class="mapping">

Get the `withheldInformationItem` object created for BT-195(BT-540)-LotsGroup and `ancestor::cac:ProcurementProjectLot[cbc:ID schemeName="LotsGroup"]`. Add a `.rationaleClassification` object to it and map the value of the `cbc:ReasonCode` to `.id` and the `cbc:ReasonCode[@listName]` to `.scheme`. Look up the code in the <a href="https://op.europa.eu/en/web/eu-vocabularies/concept-scheme/-/resource?uri=http://publications.europa.eu/resource/authority/non-publication-justification">authority table</a>, map its label to `.description` and its URI to `.uri`.

```xml
<efac:FieldsPrivacy>
  <cbc:ReasonCode listName="non-publication-justification">oth-int</cbc:ReasonCode>
</efac:FieldsPrivacy>
```

```json
{
  "withheldInformation": [
    {
      "rationaleClassification": {
        "scheme": "non-publication-justification",
        "id": "oth-int",
        "description": "Other public interest",
        "uri": "http://publications.europa.eu/resource/authority/non-publication-justification/oth-int"
      }
    }
  ]
}
```

</td>
      </tr>
      <tr id="BT-197(BT-541)-Lot">
        <td class="field break-all">
            <p><b>BT-197(BT-541)-Lot</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/withheld-publication.html#lotsGroupOfLotsLevelSection"></a><br>Unpublished Justification Code</p><p><i>BT-197:</i> The justification for not immediately publishing a field.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='Lot']/cac:TenderingTerms/cac:AwardingTerms/cac:AwardingCriterion/cac:SubordinateAwardingCriterion/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:AwardCriterionParameter/efac:FieldsPrivacy[efbc:FieldIdentifierCode/text()='awa-cri-num']/cbc:ReasonCode</span></code>
        </td>
        <td class="mapping">

Get the `withheldInformationItem` object created for BT-195(BT-541)-Lot and `ancestor::cac:ProcurementProjectLot[cbc:ID schemeName="Lot"]`. Add a `.rationaleClassification` object to it and map the value of the `cbc:ReasonCode` to `.id` and the `cbc:ReasonCode[@listName]` to `.scheme`. Look up the code in the <a href="https://op.europa.eu/en/web/eu-vocabularies/concept-scheme/-/resource?uri=http://publications.europa.eu/resource/authority/non-publication-justification">authority table</a>, map its label to `.description` and its URI to `.uri`.

```xml
<efac:FieldsPrivacy>
  <cbc:ReasonCode listName="non-publication-justification">oth-int</cbc:ReasonCode>
</efac:FieldsPrivacy>
```

```json
{
  "withheldInformation": [
    {
      "rationaleClassification": {
        "scheme": "non-publication-justification",
        "id": "oth-int",
        "description": "Other public interest",
        "uri": "http://publications.europa.eu/resource/authority/non-publication-justification/oth-int"
      }
    }
  ]
}
```

</td>
      </tr>
      <tr id="BT-197(BT-541)-LotsGroup">
        <td class="field break-all">
            <p><b>BT-197(BT-541)-LotsGroup</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/withheld-publication.html#lotsGroupOfLotsLevelSection"></a><br>Unpublished Justification Code</p><p><i>BT-197:</i> The justification for not immediately publishing a field.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='LotsGroup']/cac:TenderingTerms/cac:AwardingTerms/cac:AwardingCriterion/cac:SubordinateAwardingCriterion/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:AwardCriterionParameter/efac:FieldsPrivacy[efbc:FieldIdentifierCode/text()='awa-cri-num']/cbc:ReasonCode</span></code>
        </td>
        <td class="mapping">

Get the `withheldInformationItem` object created for BT-195(BT-541)-LotsGroup and `ancestor::cac:ProcurementProjectLot[cbc:ID schemeName="LotsGroup"]`. Add a `.rationaleClassification` object to it and map the value of the `cbc:ReasonCode` to `.id` and the `cbc:ReasonCode[@listName]` to `.scheme`. Look up the code in the <a href="https://op.europa.eu/en/web/eu-vocabularies/concept-scheme/-/resource?uri=http://publications.europa.eu/resource/authority/non-publication-justification">authority table</a>, map its label to `.description` and its URI to `.uri`.

```xml
<efac:FieldsPrivacy>
  <cbc:ReasonCode listName="non-publication-justification">oth-int</cbc:ReasonCode>
</efac:FieldsPrivacy>
```

```json
{
  "withheldInformation": [
    {
      "rationaleClassification": {
        "scheme": "non-publication-justification",
        "id": "oth-int",
        "description": "Other public interest",
        "uri": "http://publications.europa.eu/resource/authority/non-publication-justification/oth-int"
      }
    }
  ]
}
```

</td>
      </tr>
      <tr id="BT-197(BT-5421)-Lot">
        <td class="field break-all">
            <p><b>BT-197(BT-5421)-Lot</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/withheld-publication.html#lotsGroupOfLotsLevelSection"></a><br>Unpublished Justification Code</p><p><i>BT-197:</i> The justification for not immediately publishing a field.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='Lot']/cac:TenderingTerms/cac:AwardingTerms/cac:AwardingCriterion/cac:SubordinateAwardingCriterion/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:AwardCriterionParameter[efbc:ParameterCode/@listName='number-weight']/efac:FieldsPrivacy[efbc:FieldIdentifierCode/text()='awa-cri-wei']/cbc:ReasonCode</span></code>
        </td>
        <td class="mapping">

Get the `withheldInformationItem` object created for BT-195(BT-5421)-Lot and `ancestor::cac:ProcurementProjectLot[cbc:ID schemeName="Lot"]`. Add a `.rationaleClassification` object to it and map the value of the `cbc:ReasonCode` to `.id` and the `cbc:ReasonCode[@listName]` to `.scheme`. Look up the code in the <a href="https://op.europa.eu/en/web/eu-vocabularies/concept-scheme/-/resource?uri=http://publications.europa.eu/resource/authority/non-publication-justification">authority table</a>, map its label to `.description` and its URI to `.uri`.

```xml
<efac:FieldsPrivacy>
  <cbc:ReasonCode listName="non-publication-justification">oth-int</cbc:ReasonCode>
</efac:FieldsPrivacy>
```

```json
{
  "withheldInformation": [
    {
      "rationaleClassification": {
        "scheme": "non-publication-justification",
        "id": "oth-int",
        "description": "Other public interest",
        "uri": "http://publications.europa.eu/resource/authority/non-publication-justification/oth-int"
      }
    }
  ]
}
```

</td>
      </tr>
      <tr id="BT-197(BT-5421)-LotsGroup">
        <td class="field break-all">
            <p><b>BT-197(BT-5421)-LotsGroup</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/withheld-publication.html#lotsGroupOfLotsLevelSection"></a><br>Unpublished Justification Code</p><p><i>BT-197:</i> The justification for not immediately publishing a field.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='LotsGroup']/cac:TenderingTerms/cac:AwardingTerms/cac:AwardingCriterion/cac:SubordinateAwardingCriterion/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:AwardCriterionParameter[efbc:ParameterCode/@listName='number-weight']/efac:FieldsPrivacy[efbc:FieldIdentifierCode/text()='awa-cri-wei']/cbc:ReasonCode</span></code>
        </td>
        <td class="mapping">

Get the `withheldInformationItem` object created for BT-195(BT-5421)-LotsGroup and `ancestor::cac:ProcurementProjectLot[cbc:ID schemeName="LotsGroup"]`. Add a `.rationaleClassification` object to it and map the value of the `cbc:ReasonCode` to `.id` and the `cbc:ReasonCode[@listName]` to `.scheme`. Look up the code in the <a href="https://op.europa.eu/en/web/eu-vocabularies/concept-scheme/-/resource?uri=http://publications.europa.eu/resource/authority/non-publication-justification">authority table</a>, map its label to `.description` and its URI to `.uri`.

```xml
<efac:FieldsPrivacy>
  <cbc:ReasonCode listName="non-publication-justification">oth-int</cbc:ReasonCode>
</efac:FieldsPrivacy>
```

```json
{
  "withheldInformation": [
    {
      "rationaleClassification": {
        "scheme": "non-publication-justification",
        "id": "oth-int",
        "description": "Other public interest",
        "uri": "http://publications.europa.eu/resource/authority/non-publication-justification/oth-int"
      }
    }
  ]
}
```

</td>
      </tr>
      <tr id="BT-197(BT-5422)-Lot">
        <td class="field break-all">
            <p><b>BT-197(BT-5422)-Lot</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/withheld-publication.html#lotsGroupOfLotsLevelSection"></a><br>Unpublished Justification Code</p><p><i>BT-197:</i> The justification for not immediately publishing a field.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='Lot']/cac:TenderingTerms/cac:AwardingTerms/cac:AwardingCriterion/cac:SubordinateAwardingCriterion/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:AwardCriterionParameter[efbc:ParameterCode/@listName='number-fixed']/efac:FieldsPrivacy[efbc:FieldIdentifierCode/text()='awa-cri-fix']/cbc:ReasonCode</span></code>
        </td>
        <td class="mapping">

Get the `withheldInformationItem` object created for BT-195(BT-5422)-Lot and `ancestor::cac:ProcurementProjectLot[cbc:ID schemeName="Lot"]`. Add a `.rationaleClassification` object to it and map the value of the `cbc:ReasonCode` to `.id` and the `cbc:ReasonCode[@listName]` to `.scheme`. Look up the code in the <a href="https://op.europa.eu/en/web/eu-vocabularies/concept-scheme/-/resource?uri=http://publications.europa.eu/resource/authority/non-publication-justification">authority table</a>, map its label to `.description` and its URI to `.uri`.

```xml
<efac:FieldsPrivacy>
  <cbc:ReasonCode listName="non-publication-justification">oth-int</cbc:ReasonCode>
</efac:FieldsPrivacy>
```

```json
{
  "withheldInformation": [
    {
      "rationaleClassification": {
        "scheme": "non-publication-justification",
        "id": "oth-int",
        "description": "Other public interest",
        "uri": "http://publications.europa.eu/resource/authority/non-publication-justification/oth-int"
      }
    }
  ]
}
```

</td>
      </tr>
      <tr id="BT-197(BT-5422)-LotsGroup">
        <td class="field break-all">
            <p><b>BT-197(BT-5422)-LotsGroup</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/withheld-publication.html#lotsGroupOfLotsLevelSection"></a><br>Unpublished Justification Code</p><p><i>BT-197:</i> The justification for not immediately publishing a field.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='LotsGroup']/cac:TenderingTerms/cac:AwardingTerms/cac:AwardingCriterion/cac:SubordinateAwardingCriterion/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:AwardCriterionParameter[efbc:ParameterCode/@listName='number-fixed']/efac:FieldsPrivacy[efbc:FieldIdentifierCode/text()='awa-cri-fix']/cbc:ReasonCode</span></code>
        </td>
        <td class="mapping">

Get the `withheldInformationItem` object created for BT-195(BT-5422)-LotsGroup and `ancestor::cac:ProcurementProjectLot[cbc:ID schemeName="LotsGroup"]`. Add a `.rationaleClassification` object to it and map the value of the `cbc:ReasonCode` to `.id` and the `cbc:ReasonCode[@listName]` to `.scheme`. Look up the code in the <a href="https://op.europa.eu/en/web/eu-vocabularies/concept-scheme/-/resource?uri=http://publications.europa.eu/resource/authority/non-publication-justification">authority table</a>, map its label to `.description` and its URI to `.uri`.

```xml
<efac:FieldsPrivacy>
  <cbc:ReasonCode listName="non-publication-justification">oth-int</cbc:ReasonCode>
</efac:FieldsPrivacy>
```

```json
{
  "withheldInformation": [
    {
      "rationaleClassification": {
        "scheme": "non-publication-justification",
        "id": "oth-int",
        "description": "Other public interest",
        "uri": "http://publications.europa.eu/resource/authority/non-publication-justification/oth-int"
      }
    }
  ]
}
```

</td>
      </tr>
      <tr id="BT-197(BT-5423)-Lot">
        <td class="field break-all">
            <p><b>BT-197(BT-5423)-Lot</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/withheld-publication.html#lotsGroupOfLotsLevelSection"></a><br>Unpublished Justification Code</p><p><i>BT-197:</i> The justification for not immediately publishing a field.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='Lot']/cac:TenderingTerms/cac:AwardingTerms/cac:AwardingCriterion/cac:SubordinateAwardingCriterion/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:AwardCriterionParameter[efbc:ParameterCode/@listName='number-threshold']/efac:FieldsPrivacy[efbc:FieldIdentifierCode/text()='awa-cri-thr']/cbc:ReasonCode</span></code>
        </td>
        <td class="mapping">

Get the `withheldInformationItem` object created for BT-195(BT-5423)-Lot and `ancestor::cac:ProcurementProjectLot[cbc:ID schemeName="Lot"]`. Add a `.rationaleClassification` object to it and map the value of the `cbc:ReasonCode` to `.id` and the `cbc:ReasonCode[@listName]` to `.scheme`. Look up the code in the <a href="https://op.europa.eu/en/web/eu-vocabularies/concept-scheme/-/resource?uri=http://publications.europa.eu/resource/authority/non-publication-justification">authority table</a>, map its label to `.description` and its URI to `.uri`.

```xml
<efac:FieldsPrivacy>
  <cbc:ReasonCode listName="non-publication-justification">oth-int</cbc:ReasonCode>
</efac:FieldsPrivacy>
```

```json
{
  "withheldInformation": [
    {
      "rationaleClassification": {
        "scheme": "non-publication-justification",
        "id": "oth-int",
        "description": "Other public interest",
        "uri": "http://publications.europa.eu/resource/authority/non-publication-justification/oth-int"
      }
    }
  ]
}
```

</td>
      </tr>
      <tr id="BT-197(BT-5423)-LotsGroup">
        <td class="field break-all">
            <p><b>BT-197(BT-5423)-LotsGroup</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/withheld-publication.html#lotsGroupOfLotsLevelSection"></a><br>Unpublished Justification Code</p><p><i>BT-197:</i> The justification for not immediately publishing a field.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='LotsGroup']/cac:TenderingTerms/cac:AwardingTerms/cac:AwardingCriterion/cac:SubordinateAwardingCriterion/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:AwardCriterionParameter[efbc:ParameterCode/@listName='number-threshold']/efac:FieldsPrivacy[efbc:FieldIdentifierCode/text()='awa-cri-thr']/cbc:ReasonCode</span></code>
        </td>
        <td class="mapping">

Get the `withheldInformationItem` object created for BT-195(BT-5423)-LotsGroup and `ancestor::cac:ProcurementProjectLot[cbc:ID schemeName="LotsGroup"]`. Add a `.rationaleClassification` object to it and map the value of the `cbc:ReasonCode` to `.id` and the `cbc:ReasonCode[@listName]` to `.scheme`. Look up the code in the <a href="https://op.europa.eu/en/web/eu-vocabularies/concept-scheme/-/resource?uri=http://publications.europa.eu/resource/authority/non-publication-justification">authority table</a>, map its label to `.description` and its URI to `.uri`.

```xml
<efac:FieldsPrivacy>
  <cbc:ReasonCode listName="non-publication-justification">oth-int</cbc:ReasonCode>
</efac:FieldsPrivacy>
```

```json
{
  "withheldInformation": [
    {
      "rationaleClassification": {
        "scheme": "non-publication-justification",
        "id": "oth-int",
        "description": "Other public interest",
        "uri": "http://publications.europa.eu/resource/authority/non-publication-justification/oth-int"
      }
    }
  ]
}
```

</td>
      </tr>
      <tr id="BT-197(BT-543)-Lot">
        <td class="field break-all">
            <p><b>BT-197(BT-543)-Lot</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/withheld-publication.html#lotsGroupOfLotsLevelSection"></a><br>Unpublished Justification Code</p><p><i>BT-197:</i> The justification for not immediately publishing a field.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='Lot']/cac:TenderingTerms/cac:AwardingTerms/cac:AwardingCriterion/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:FieldsPrivacy[efbc:FieldIdentifierCode/text()='awa-cri-com']/cbc:ReasonCode</span></code>
        </td>
        <td class="mapping">

Get the `withheldInformationItem` object created for BT-195(BT-543)-Lot and `ancestor::cac:ProcurementProjectLot[cbc:ID schemeName="Lot"]`. Add a `.rationaleClassification` object to it and map the value of the `cbc:ReasonCode` to `.id` and the `cbc:ReasonCode[@listName]` to `.scheme`. Look up the code in the <a href="https://op.europa.eu/en/web/eu-vocabularies/concept-scheme/-/resource?uri=http://publications.europa.eu/resource/authority/non-publication-justification">authority table</a>, map its label to `.description` and its URI to `.uri`.

```xml
<efac:FieldsPrivacy>
  <cbc:ReasonCode listName="non-publication-justification">oth-int</cbc:ReasonCode>
</efac:FieldsPrivacy>
```

```json
{
  "withheldInformation": [
    {
      "rationaleClassification": {
        "scheme": "non-publication-justification",
        "id": "oth-int",
        "description": "Other public interest",
        "uri": "http://publications.europa.eu/resource/authority/non-publication-justification/oth-int"
      }
    }
  ]
}
```

</td>
      </tr>
      <tr id="BT-197(BT-543)-LotsGroup">
        <td class="field break-all">
            <p><b>BT-197(BT-543)-LotsGroup</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/withheld-publication.html#lotsGroupOfLotsLevelSection"></a><br>Unpublished Justification Code</p><p><i>BT-197:</i> The justification for not immediately publishing a field.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='LotsGroup']/cac:TenderingTerms/cac:AwardingTerms/cac:AwardingCriterion/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:FieldsPrivacy[efbc:FieldIdentifierCode/text()='awa-cri-com']/cbc:ReasonCode</span></code>
        </td>
        <td class="mapping">

Get the `withheldInformationItem` object created for BT-195(BT-543)-LotsGroup and `ancestor::cac:ProcurementProjectLot[cbc:ID schemeName="LotsGroup"]`. Add a `.rationaleClassification` object to it and map the value of the `cbc:ReasonCode` to `.id` and the `cbc:ReasonCode[@listName]` to `.scheme`. Look up the code in the <a href="https://op.europa.eu/en/web/eu-vocabularies/concept-scheme/-/resource?uri=http://publications.europa.eu/resource/authority/non-publication-justification">authority table</a>, map its label to `.description` and its URI to `.uri`.

```xml
<efac:FieldsPrivacy>
  <cbc:ReasonCode listName="non-publication-justification">oth-int</cbc:ReasonCode>
</efac:FieldsPrivacy>
```

```json
{
  "withheldInformation": [
    {
      "rationaleClassification": {
        "scheme": "non-publication-justification",
        "id": "oth-int",
        "description": "Other public interest",
        "uri": "http://publications.europa.eu/resource/authority/non-publication-justification/oth-int"
      }
    }
  ]
}
```

</td>
      </tr>
      <tr id="BT-197(BT-553)-Tender">
        <td class="field break-all">
            <p><b>BT-197(BT-553)-Tender</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/withheld-publication.html#lotTenderLevelSection"></a><br>Unpublished Justification Code</p><p><i>BT-197:</i> The justification for not immediately publishing a field.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:NoticeResult/efac:LotTender/efac:SubcontractingTerm/efac:FieldsPrivacy[efbc:FieldIdentifierCode/text()='sub-val']/cbc:ReasonCode</span></code>
        </td>
        <td class="mapping">

Get the `withheldInformationItem` object created for BT-195(BT-553)-Tender and `ancestor::efac:LotTender`. Add a `.rationaleClassification` object to it and map the value of the `cbc:ReasonCode` to `.id` and the `cbc:ReasonCode[@listName]` to `.scheme`. Look up the code in the <a href="https://op.europa.eu/en/web/eu-vocabularies/concept-scheme/-/resource?uri=http://publications.europa.eu/resource/authority/non-publication-justification">authority table</a>, map its label to `.description` and its URI to `.uri`.

```xml
<efac:FieldsPrivacy>
  <cbc:ReasonCode listName="non-publication-justification">oth-int</cbc:ReasonCode>
</efac:FieldsPrivacy>
```

```json
{
  "withheldInformation": [
    {
      "rationaleClassification": {
        "scheme": "non-publication-justification",
        "id": "oth-int",
        "description": "Other public interest",
        "uri": "http://publications.europa.eu/resource/authority/non-publication-justification/oth-int"
      }
    }
  ]
}
```

</td>
      </tr>
      <tr id="BT-197(BT-554)-Tender">
        <td class="field break-all">
            <p><b>BT-197(BT-554)-Tender</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/withheld-publication.html#lotTenderLevelSection"></a><br>Unpublished Justification Code</p><p><i>BT-197:</i> The justification for not immediately publishing a field.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:NoticeResult/efac:LotTender/efac:SubcontractingTerm/efac:FieldsPrivacy[efbc:FieldIdentifierCode/text()='sub-des']/cbc:ReasonCode</span></code>
        </td>
        <td class="mapping">

Get the `withheldInformationItem` object created for BT-195(BT-554)-Tender and `ancestor::efac:LotTender`. Add a `.rationaleClassification` object to it and map the value of the `cbc:ReasonCode` to `.id` and the `cbc:ReasonCode[@listName]` to `.scheme`. Look up the code in the <a href="https://op.europa.eu/en/web/eu-vocabularies/concept-scheme/-/resource?uri=http://publications.europa.eu/resource/authority/non-publication-justification">authority table</a>, map its label to `.description` and its URI to `.uri`.

```xml
<efac:FieldsPrivacy>
  <cbc:ReasonCode listName="non-publication-justification">oth-int</cbc:ReasonCode>
</efac:FieldsPrivacy>
```

```json
{
  "withheldInformation": [
    {
      "rationaleClassification": {
        "scheme": "non-publication-justification",
        "id": "oth-int",
        "description": "Other public interest",
        "uri": "http://publications.europa.eu/resource/authority/non-publication-justification/oth-int"
      }
    }
  ]
}
```

</td>
      </tr>
      <tr id="BT-197(BT-555)-Tender">
        <td class="field break-all">
            <p><b>BT-197(BT-555)-Tender</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/withheld-publication.html#lotTenderLevelSection"></a><br>Unpublished Justification Code</p><p><i>BT-197:</i> The justification for not immediately publishing a field.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:NoticeResult/efac:LotTender/efac:SubcontractingTerm/efac:FieldsPrivacy[efbc:FieldIdentifierCode/text()='sub-per']/cbc:ReasonCode</span></code>
        </td>
        <td class="mapping">

Get the `withheldInformationItem` object created for BT-195(BT-555)-Tender and `ancestor::efac:LotTender`. Add a `.rationaleClassification` object to it and map the value of the `cbc:ReasonCode` to `.id` and the `cbc:ReasonCode[@listName]` to `.scheme`. Look up the code in the <a href="https://op.europa.eu/en/web/eu-vocabularies/concept-scheme/-/resource?uri=http://publications.europa.eu/resource/authority/non-publication-justification">authority table</a>, map its label to `.description` and its URI to `.uri`.

```xml
<efac:FieldsPrivacy>
  <cbc:ReasonCode listName="non-publication-justification">oth-int</cbc:ReasonCode>
</efac:FieldsPrivacy>
```

```json
{
  "withheldInformation": [
    {
      "rationaleClassification": {
        "scheme": "non-publication-justification",
        "id": "oth-int",
        "description": "Other public interest",
        "uri": "http://publications.europa.eu/resource/authority/non-publication-justification/oth-int"
      }
    }
  ]
}
```

</td>
      </tr>
      <tr id="BT-197(BT-556)-NoticeResult">
        <td class="field break-all">
            <p><b>BT-197(BT-556)-NoticeResult</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/withheld-publication.html#_notice_result_level"></a><br>Unpublished Justification Code</p><p><i>BT-197:</i> The justification for not immediately publishing a field.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:NoticeResult/efac:GroupFramework/efac:FieldsPrivacy[efbc:FieldIdentifierCode/text()='gro-max-ide']/cbc:ReasonCode</span></code>
        </td>
        <td class="mapping">

Discard.

```xml
<efac:FieldsPrivacy>
  <cbc:ReasonCode listName="non-publication-justification">oth-int</cbc:ReasonCode>
</efac:FieldsPrivacy>
```



</td>
      </tr>
      <tr id="BT-197(BT-635)-LotResult">
        <td class="field break-all">
            <p><b>BT-197(BT-635)-LotResult</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/withheld-publication.html#lotResultLevelSection"></a><br>Unpublished Justification Code</p><p><i>BT-197:</i> The justification for not immediately publishing a field.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:NoticeResult/efac:LotResult/efac:AppealRequestsStatistics[efbc:StatisticsCode/@listName='irregularity-type']/efac:FieldsPrivacy[efbc:FieldIdentifierCode/text()='buy-rev-cou']/cbc:ReasonCode</span></code>
        </td>
        <td class="mapping">

Get the `withheldInformationItem` object created for BT-195(BT-635)-LotResult and `ancestor::efac:LotResult`. Add a `.rationaleClassification` object to it and map the value of the `cbc:ReasonCode` to `.id` and the `cbc:ReasonCode[@listName]` to `.scheme`. Look up the code in the <a href="https://op.europa.eu/en/web/eu-vocabularies/concept-scheme/-/resource?uri=http://publications.europa.eu/resource/authority/non-publication-justification">authority table</a>, map its label to `.description` and its URI to `.uri`.

```xml
<efac:FieldsPrivacy>
  <cbc:ReasonCode listName="non-publication-justification">oth-int</cbc:ReasonCode>
</efac:FieldsPrivacy>
```

```json
{
  "withheldInformation": [
    {
      "rationaleClassification": {
        "scheme": "non-publication-justification",
        "id": "oth-int",
        "description": "Other public interest",
        "uri": "http://publications.europa.eu/resource/authority/non-publication-justification/oth-int"
      }
    }
  ]
}
```

</td>
      </tr>
      <tr id="BT-197(BT-636)-LotResult">
        <td class="field break-all">
            <p><b>BT-197(BT-636)-LotResult</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/withheld-publication.html#lotResultLevelSection"></a><br>Unpublished Justification Code</p><p><i>BT-197:</i> The justification for not immediately publishing a field.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:NoticeResult/efac:LotResult/efac:AppealRequestsStatistics[efbc:StatisticsCode/@listName='irregularity-type']/efac:FieldsPrivacy[efbc:FieldIdentifierCode/text()='buy-rev-typ']/cbc:ReasonCode</span></code>
        </td>
        <td class="mapping">

Get the `withheldInformationItem` object created for BT-195(BT-636)-LotResult and `ancestor::efac:LotResult`. Add a `.rationaleClassification` object to it and map the value of the `cbc:ReasonCode` to `.id` and the `cbc:ReasonCode[@listName]` to `.scheme`. Look up the code in the <a href="https://op.europa.eu/en/web/eu-vocabularies/concept-scheme/-/resource?uri=http://publications.europa.eu/resource/authority/non-publication-justification">authority table</a>, map its label to `.description` and its URI to `.uri`.

```xml
<efac:FieldsPrivacy>
  <cbc:ReasonCode listName="non-publication-justification">oth-int</cbc:ReasonCode>
</efac:FieldsPrivacy>
```

```json
{
  "withheldInformation": [
    {
      "rationaleClassification": {
        "scheme": "non-publication-justification",
        "id": "oth-int",
        "description": "Other public interest",
        "uri": "http://publications.europa.eu/resource/authority/non-publication-justification/oth-int"
      }
    }
  ]
}
```

</td>
      </tr>
      <tr id="BT-197(BT-709)-LotResult">
        <td class="field break-all">
            <p><b>BT-197(BT-709)-LotResult</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/withheld-publication.html#lotResultLevelSection"></a><br>Unpublished Justification Code</p><p><i>BT-197:</i> The justification for not immediately publishing a field.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:NoticeResult/efac:LotResult/efac:FrameworkAgreementValues/efac:FieldsPrivacy[efbc:FieldIdentifierCode/text()='max-val']/cbc:ReasonCode</span></code>
        </td>
        <td class="mapping">

Get the `withheldInformationItem` object created for BT-195(BT-709)-LotResult and `ancestor::efac:LotResult`. Add a `.rationaleClassification` object to it and map the value of the `cbc:ReasonCode` to `.id` and the `cbc:ReasonCode[@listName]` to `.scheme`. Look up the code in the <a href="https://op.europa.eu/en/web/eu-vocabularies/concept-scheme/-/resource?uri=http://publications.europa.eu/resource/authority/non-publication-justification">authority table</a>, map its label to `.description` and its URI to `.uri`.

```xml
<efac:FieldsPrivacy>
  <cbc:ReasonCode listName="non-publication-justification">oth-int</cbc:ReasonCode>
</efac:FieldsPrivacy>
```

```json
{
  "withheldInformation": [
    {
      "rationaleClassification": {
        "scheme": "non-publication-justification",
        "id": "oth-int",
        "description": "Other public interest",
        "uri": "http://publications.europa.eu/resource/authority/non-publication-justification/oth-int"
      }
    }
  ]
}
```

</td>
      </tr>
      <tr id="BT-197(BT-710)-LotResult">
        <td class="field break-all">
            <p><b>BT-197(BT-710)-LotResult</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/withheld-publication.html#lotResultLevelSection"></a><br>Unpublished Justification Code</p><p><i>BT-197:</i> The justification for not immediately publishing a field.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:NoticeResult/efac:LotResult/efac:FieldsPrivacy[efbc:FieldIdentifierCode/text()='ten-val-low']/cbc:ReasonCode</span></code>
        </td>
        <td class="mapping">

Get the `withheldInformationItem` object created for BT-195(BT-710)-LotResult and `ancestor::efac:LotResult`. Add a `.rationaleClassification` object to it and map the value of the `cbc:ReasonCode` to `.id` and the `cbc:ReasonCode[@listName]` to `.scheme`. Look up the code in the <a href="https://op.europa.eu/en/web/eu-vocabularies/concept-scheme/-/resource?uri=http://publications.europa.eu/resource/authority/non-publication-justification">authority table</a>, map its label to `.description` and its URI to `.uri`.

```xml
<efac:FieldsPrivacy>
  <cbc:ReasonCode listName="non-publication-justification">oth-int</cbc:ReasonCode>
</efac:FieldsPrivacy>
```

```json
{
  "withheldInformation": [
    {
      "rationaleClassification": {
        "scheme": "non-publication-justification",
        "id": "oth-int",
        "description": "Other public interest",
        "uri": "http://publications.europa.eu/resource/authority/non-publication-justification/oth-int"
      }
    }
  ]
}
```

</td>
      </tr>
      <tr id="BT-197(BT-711)-LotResult">
        <td class="field break-all">
            <p><b>BT-197(BT-711)-LotResult</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/withheld-publication.html#lotResultLevelSection"></a><br>Unpublished Justification Code</p><p><i>BT-197:</i> The justification for not immediately publishing a field.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:NoticeResult/efac:LotResult/efac:FieldsPrivacy[efbc:FieldIdentifierCode/text()='ten-val-hig']/cbc:ReasonCode</span></code>
        </td>
        <td class="mapping">

Get the `withheldInformationItem` object created for BT-195(BT-711)-LotResult and `ancestor::efac:LotResult`. Add a `.rationaleClassification` object to it and map the value of the `cbc:ReasonCode` to `.id` and the `cbc:ReasonCode[@listName]` to `.scheme`. Look up the code in the <a href="https://op.europa.eu/en/web/eu-vocabularies/concept-scheme/-/resource?uri=http://publications.europa.eu/resource/authority/non-publication-justification">authority table</a>, map its label to `.description` and its URI to `.uri`.

```xml
<efac:FieldsPrivacy>
  <cbc:ReasonCode listName="non-publication-justification">oth-int</cbc:ReasonCode>
</efac:FieldsPrivacy>
```

```json
{
  "withheldInformation": [
    {
      "rationaleClassification": {
        "scheme": "non-publication-justification",
        "id": "oth-int",
        "description": "Other public interest",
        "uri": "http://publications.europa.eu/resource/authority/non-publication-justification/oth-int"
      }
    }
  ]
}
```

</td>
      </tr>
      <tr id="BT-197(BT-712)-LotResult">
        <td class="field break-all">
            <p><b>BT-197(BT-712)-LotResult</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/withheld-publication.html#lotResultLevelSection"></a><br>Unpublished Justification Code</p><p><i>BT-197:</i> The justification for not immediately publishing a field.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:NoticeResult/efac:LotResult/efac:AppealRequestsStatistics[efbc:StatisticsCode/@listName='review-type']/efac:FieldsPrivacy[efbc:FieldIdentifierCode/text()='rev-req']/cbc:ReasonCode</span></code>
        </td>
        <td class="mapping">

Get the `withheldInformationItem` object created for BT-195(BT-712)-LotResult and `ancestor::efac:LotResult`. Add a `.rationaleClassification` object to it and map the value of the `cbc:ReasonCode` to `.id` and the `cbc:ReasonCode[@listName]` to `.scheme`. Look up the code in the <a href="https://op.europa.eu/en/web/eu-vocabularies/concept-scheme/-/resource?uri=http://publications.europa.eu/resource/authority/non-publication-justification">authority table</a>, map its label to `.description` and its URI to `.uri`.

```xml
<efac:FieldsPrivacy>
  <cbc:ReasonCode listName="non-publication-justification">oth-int</cbc:ReasonCode>
</efac:FieldsPrivacy>
```

```json
{
  "withheldInformation": [
    {
      "rationaleClassification": {
        "scheme": "non-publication-justification",
        "id": "oth-int",
        "description": "Other public interest",
        "uri": "http://publications.europa.eu/resource/authority/non-publication-justification/oth-int"
      }
    }
  ]
}
```

</td>
      </tr>
      <tr id="BT-197(BT-720)-Tender">
        <td class="field break-all">
            <p><b>BT-197(BT-720)-Tender</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/withheld-publication.html#lotTenderLevelSection"></a><br>Unpublished Justification Code</p><p><i>BT-197:</i> The justification for not immediately publishing a field.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:NoticeResult/efac:LotTender/efac:FieldsPrivacy[efbc:FieldIdentifierCode/text()='win-ten-val']/cbc:ReasonCode</span></code>
        </td>
        <td class="mapping">

Get the `withheldInformationItem` object created for BT-195(BT-720)-Tender and `ancestor::efac:LotTender`. Add a `.rationaleClassification` object to it and map the value of the `cbc:ReasonCode` to `.id` and the `cbc:ReasonCode[@listName]` to `.scheme`. Look up the code in the <a href="https://op.europa.eu/en/web/eu-vocabularies/concept-scheme/-/resource?uri=http://publications.europa.eu/resource/authority/non-publication-justification">authority table</a>, map its label to `.description` and its URI to `.uri`.

```xml
<efac:FieldsPrivacy>
  <cbc:ReasonCode listName="non-publication-justification">oth-int</cbc:ReasonCode>
</efac:FieldsPrivacy>
```

```json
{
  "withheldInformation": [
    {
      "rationaleClassification": {
        "scheme": "non-publication-justification",
        "id": "oth-int",
        "description": "Other public interest",
        "uri": "http://publications.europa.eu/resource/authority/non-publication-justification/oth-int"
      }
    }
  ]
}
```

</td>
      </tr>
      <tr id="BT-197(BT-730)-Tender">
        <td class="field break-all">
            <p><b>BT-197(BT-730)-Tender</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/withheld-publication.html#lotTenderLevelSection"></a><br>Unpublished Justification Code</p><p><i>BT-197:</i> The justification for not immediately publishing a field.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:NoticeResult/efac:LotTender/efac:SubcontractingTerm/efac:FieldsPrivacy[efbc:FieldIdentifierCode/text()='sub-val-kno']/cbc:ReasonCode</span></code>
        </td>
        <td class="mapping">

Discard. BT-730 is discarded as it is implied by BT-553.

```xml
<efac:FieldsPrivacy>
  <cbc:ReasonCode listName="non-publication-justification">oth-int</cbc:ReasonCode>
</efac:FieldsPrivacy>
```



</td>
      </tr>
      <tr id="BT-197(BT-731)-Tender">
        <td class="field break-all">
            <p><b>BT-197(BT-731)-Tender</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/withheld-publication.html#lotTenderLevelSection"></a><br>Unpublished Justification Code</p><p><i>BT-197:</i> The justification for not immediately publishing a field.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:NoticeResult/efac:LotTender/efac:SubcontractingTerm/efac:FieldsPrivacy[efbc:FieldIdentifierCode/text()='sub-per-kno']/cbc:ReasonCode</span></code>
        </td>
        <td class="mapping">

Discard. BT-731 is discarded as it is implied by BT-555.

```xml
<efac:FieldsPrivacy>
  <cbc:ReasonCode listName="non-publication-justification">oth-int</cbc:ReasonCode>
</efac:FieldsPrivacy>
```



</td>
      </tr>
      <tr id="BT-197(BT-733)-Lot">
        <td class="field break-all">
            <p><b>BT-197(BT-733)-Lot</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/withheld-publication.html#lotsGroupOfLotsLevelSection"></a><br>Unpublished Justification Code</p><p><i>BT-197:</i> The justification for not immediately publishing a field.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='Lot']/cac:TenderingTerms/cac:AwardingTerms/cac:AwardingCriterion/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:FieldsPrivacy[efbc:FieldIdentifierCode/text()='awa-cri-ord']/cbc:ReasonCode</span></code>
        </td>
        <td class="mapping">

Get the `withheldInformationItem` object created for BT-195(BT-733)-Lot and `ancestor::cac:ProcurementProjectLot[cbc:ID schemeName="Lot"]`. Add a `.rationaleClassification` object to it and map the value of the `cbc:ReasonCode` to `.id` and the `cbc:ReasonCode[@listName]` to `.scheme`. Look up the code in the <a href="https://op.europa.eu/en/web/eu-vocabularies/concept-scheme/-/resource?uri=http://publications.europa.eu/resource/authority/non-publication-justification">authority table</a>, map its label to `.description` and its URI to `.uri`.

```xml
<efac:FieldsPrivacy>
  <cbc:ReasonCode listName="non-publication-justification">oth-int</cbc:ReasonCode>
</efac:FieldsPrivacy>
```

```json
{
  "withheldInformation": [
    {
      "rationaleClassification": {
        "scheme": "non-publication-justification",
        "id": "oth-int",
        "description": "Other public interest",
        "uri": "http://publications.europa.eu/resource/authority/non-publication-justification/oth-int"
      }
    }
  ]
}
```

</td>
      </tr>
      <tr id="BT-197(BT-733)-LotsGroup">
        <td class="field break-all">
            <p><b>BT-197(BT-733)-LotsGroup</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/withheld-publication.html#lotsGroupOfLotsLevelSection"></a><br>Unpublished Justification Code</p><p><i>BT-197:</i> The justification for not immediately publishing a field.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='LotsGroup']/cac:TenderingTerms/cac:AwardingTerms/cac:AwardingCriterion/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:FieldsPrivacy[efbc:FieldIdentifierCode/text()='awa-cri-ord']/cbc:ReasonCode</span></code>
        </td>
        <td class="mapping">

Get the `withheldInformationItem` object created for BT-195(BT-733)-LotsGroup and `ancestor::cac:ProcurementProjectLot[cbc:ID schemeName="LotsGroup"]`. Add a `.rationaleClassification` object to it and map the value of the `cbc:ReasonCode` to `.id` and the `cbc:ReasonCode[@listName]` to `.scheme`. Look up the code in the <a href="https://op.europa.eu/en/web/eu-vocabularies/concept-scheme/-/resource?uri=http://publications.europa.eu/resource/authority/non-publication-justification">authority table</a>, map its label to `.description` and its URI to `.uri`.

```xml
<efac:FieldsPrivacy>
  <cbc:ReasonCode listName="non-publication-justification">oth-int</cbc:ReasonCode>
</efac:FieldsPrivacy>
```

```json
{
  "withheldInformation": [
    {
      "rationaleClassification": {
        "scheme": "non-publication-justification",
        "id": "oth-int",
        "description": "Other public interest",
        "uri": "http://publications.europa.eu/resource/authority/non-publication-justification/oth-int"
      }
    }
  ]
}
```

</td>
      </tr>
      <tr id="BT-197(BT-734)-Lot">
        <td class="field break-all">
            <p><b>BT-197(BT-734)-Lot</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/withheld-publication.html#lotsGroupOfLotsLevelSection"></a><br>Unpublished Justification Code</p><p><i>BT-197:</i> The justification for not immediately publishing a field.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='Lot']/cac:TenderingTerms/cac:AwardingTerms/cac:AwardingCriterion/cac:SubordinateAwardingCriterion/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:FieldsPrivacy[efbc:FieldIdentifierCode/text()='awa-cri-nam']/cbc:ReasonCode</span></code>
        </td>
        <td class="mapping">

Get the `withheldInformationItem` object created for BT-195(BT-734)-Lot and `ancestor::cac:ProcurementProjectLot[cbc:ID schemeName="Lot"]`. Add a `.rationaleClassification` object to it and map the value of the `cbc:ReasonCode` to `.id` and the `cbc:ReasonCode[@listName]` to `.scheme`. Look up the code in the <a href="https://op.europa.eu/en/web/eu-vocabularies/concept-scheme/-/resource?uri=http://publications.europa.eu/resource/authority/non-publication-justification">authority table</a>, map its label to `.description` and its URI to `.uri`.

```xml
<efac:FieldsPrivacy>
  <cbc:ReasonCode listName="non-publication-justification">oth-int</cbc:ReasonCode>
</efac:FieldsPrivacy>
```

```json
{
  "withheldInformation": [
    {
      "rationaleClassification": {
        "scheme": "non-publication-justification",
        "id": "oth-int",
        "description": "Other public interest",
        "uri": "http://publications.europa.eu/resource/authority/non-publication-justification/oth-int"
      }
    }
  ]
}
```

</td>
      </tr>
      <tr id="BT-197(BT-734)-LotsGroup">
        <td class="field break-all">
            <p><b>BT-197(BT-734)-LotsGroup</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/withheld-publication.html#lotsGroupOfLotsLevelSection"></a><br>Unpublished Justification Code</p><p><i>BT-197:</i> The justification for not immediately publishing a field.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='LotsGroup']/cac:TenderingTerms/cac:AwardingTerms/cac:AwardingCriterion/cac:SubordinateAwardingCriterion/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:FieldsPrivacy[efbc:FieldIdentifierCode/text()='awa-cri-nam']/cbc:ReasonCode</span></code>
        </td>
        <td class="mapping">

Get the `withheldInformationItem` object created for BT-195(BT-734)-LotsGroup and `ancestor::cac:ProcurementProjectLot[cbc:ID schemeName="LotsGroup"]`. Add a `.rationaleClassification` object to it and map the value of the `cbc:ReasonCode` to `.id` and the `cbc:ReasonCode[@listName]` to `.scheme`. Look up the code in the <a href="https://op.europa.eu/en/web/eu-vocabularies/concept-scheme/-/resource?uri=http://publications.europa.eu/resource/authority/non-publication-justification">authority table</a>, map its label to `.description` and its URI to `.uri`.

```xml
<efac:FieldsPrivacy>
  <cbc:ReasonCode listName="non-publication-justification">oth-int</cbc:ReasonCode>
</efac:FieldsPrivacy>
```

```json
{
  "withheldInformation": [
    {
      "rationaleClassification": {
        "scheme": "non-publication-justification",
        "id": "oth-int",
        "description": "Other public interest",
        "uri": "http://publications.europa.eu/resource/authority/non-publication-justification/oth-int"
      }
    }
  ]
}
```

</td>
      </tr>
      <tr id="BT-197(BT-759)-LotResult">
        <td class="field break-all">
            <p><b>BT-197(BT-759)-LotResult</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/withheld-publication.html#lotResultLevelSection"></a><br>Unpublished Justification Code</p><p><i>BT-197:</i> The justification for not immediately publishing a field.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:NoticeResult/efac:LotResult/efac:ReceivedSubmissionsStatistics/efac:FieldsPrivacy[efbc:FieldIdentifierCode/text()='rec-sub-cou']/cbc:ReasonCode</span></code>
        </td>
        <td class="mapping">

Get the `withheldInformationItem` object created for BT-195(BT-759)-LotResult and `ancestor::efac:LotResult`. Add a `.rationaleClassification` object to it and map the value of the `cbc:ReasonCode` to `.id` and the `cbc:ReasonCode[@listName]` to `.scheme`. Look up the code in the <a href="https://op.europa.eu/en/web/eu-vocabularies/concept-scheme/-/resource?uri=http://publications.europa.eu/resource/authority/non-publication-justification">authority table</a>, map its label to `.description` and its URI to `.uri`.

```xml
<efac:FieldsPrivacy>
  <cbc:ReasonCode listName="non-publication-justification">oth-int</cbc:ReasonCode>
</efac:FieldsPrivacy>
```

```json
{
  "withheldInformation": [
    {
      "rationaleClassification": {
        "scheme": "non-publication-justification",
        "id": "oth-int",
        "description": "Other public interest",
        "uri": "http://publications.europa.eu/resource/authority/non-publication-justification/oth-int"
      }
    }
  ]
}
```

</td>
      </tr>
      <tr id="BT-197(BT-760)-LotResult">
        <td class="field break-all">
            <p><b>BT-197(BT-760)-LotResult</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/withheld-publication.html#lotResultLevelSection"></a><br>Unpublished Justification Code</p><p><i>BT-197:</i> The justification for not immediately publishing a field.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:NoticeResult/efac:LotResult/efac:ReceivedSubmissionsStatistics/efac:FieldsPrivacy[efbc:FieldIdentifierCode/text()='rec-sub-typ']/cbc:ReasonCode</span></code>
        </td>
        <td class="mapping">

Get the `withheldInformationItem` object created for BT-195(BT-760)-LotResult and `ancestor::efac:LotResult`. Add a `.rationaleClassification` object to it and map the value of the `cbc:ReasonCode` to `.id` and the `cbc:ReasonCode[@listName]` to `.scheme`. Look up the code in the <a href="https://op.europa.eu/en/web/eu-vocabularies/concept-scheme/-/resource?uri=http://publications.europa.eu/resource/authority/non-publication-justification">authority table</a>, map its label to `.description` and its URI to `.uri`.

```xml
<efac:FieldsPrivacy>
  <cbc:ReasonCode listName="non-publication-justification">oth-int</cbc:ReasonCode>
</efac:FieldsPrivacy>
```

```json
{
  "withheldInformation": [
    {
      "rationaleClassification": {
        "scheme": "non-publication-justification",
        "id": "oth-int",
        "description": "Other public interest",
        "uri": "http://publications.europa.eu/resource/authority/non-publication-justification/oth-int"
      }
    }
  ]
}
```

</td>
      </tr>
      <tr id="BT-197(BT-773)-Tender">
        <td class="field break-all">
            <p><b>BT-197(BT-773)-Tender</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/withheld-publication.html#lotTenderLevelSection"></a><br>Unpublished Justification Code</p><p><i>BT-197:</i> The justification for not immediately publishing a field.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:NoticeResult/efac:LotTender/efac:SubcontractingTerm/efac:FieldsPrivacy[efbc:FieldIdentifierCode/text()='sub-con']/cbc:ReasonCode</span></code>
        </td>
        <td class="mapping">

Get the `withheldInformationItem` object created for BT-195(BT-773)-Tender and `ancestor::efac:LotTender`. Add a `.rationaleClassification` object to it and map the value of the `cbc:ReasonCode` to `.id` and the `cbc:ReasonCode[@listName]` to `.scheme`. Look up the code in the <a href="https://op.europa.eu/en/web/eu-vocabularies/concept-scheme/-/resource?uri=http://publications.europa.eu/resource/authority/non-publication-justification">authority table</a>, map its label to `.description` and its URI to `.uri`.

```xml
<efac:FieldsPrivacy>
  <cbc:ReasonCode listName="non-publication-justification">oth-int</cbc:ReasonCode>
</efac:FieldsPrivacy>
```

```json
{
  "withheldInformation": [
    {
      "rationaleClassification": {
        "scheme": "non-publication-justification",
        "id": "oth-int",
        "description": "Other public interest",
        "uri": "http://publications.europa.eu/resource/authority/non-publication-justification/oth-int"
      }
    }
  ]
}
```

</td>
      </tr>
      <tr id="BT-197(BT-88)-Procedure">
        <td class="field break-all">
            <p><b>BT-197(BT-88)-Procedure</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/withheld-publication.html#procedureLevelSection"></a><br>Unpublished Justification Code</p><p><i>BT-197:</i> The justification for not immediately publishing a field.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:TenderingProcess/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:FieldsPrivacy[efbc:FieldIdentifierCode/text()='pro-fea']/cbc:ReasonCode</span></code>
        </td>
        <td class="mapping">

Get the `withheldInformationItem` object created for BT-195(BT-88)-Procedure. Add a `.rationaleClassification` object to it and map the value of the `cbc:ReasonCode` to `.id` and the `cbc:ReasonCode[@listName]` to `.scheme`. Look up the code in the <a href="https://op.europa.eu/en/web/eu-vocabularies/concept-scheme/-/resource?uri=http://publications.europa.eu/resource/authority/non-publication-justification">authority table</a>, map its label to `.description` and its URI to `.uri`.

```xml
<efac:FieldsPrivacy>
  <cbc:ReasonCode listName="non-publication-justification">oth-int</cbc:ReasonCode>
</efac:FieldsPrivacy>
```

```json
{
  "withheldInformation": [
    {
      "rationaleClassification": {
        "scheme": "non-publication-justification",
        "id": "oth-int",
        "description": "Other public interest",
        "uri": "http://publications.europa.eu/resource/authority/non-publication-justification/oth-int"
      }
    }
  ]
}
```

</td>
      </tr>
      <tr id="BT-198(BT-09)-Procedure">
        <td class="field break-all">
            <p><b>BT-198(BT-09)-Procedure</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/withheld-publication.html#procedureLevelSection"></a><br>Unpublished Access Date</p><p><i>BT-198:</i> The later date at which the originally unpublished field shall be published.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:TenderingTerms/cac:ProcurementLegislationDocumentReference[cbc:ID/text()='CrossBorderLaw']/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:FieldsPrivacy[efbc:FieldIdentifierCode/text()='cro-bor-law']/efbc:PublicationDate</span></code>
        </td>
        <td class="mapping">

Get the `withheldInformationItem` object created for BT-195(BT-09)-Procedure. <a href="operations.md#convert-a-date-to-iso-format">Convert date to ISO format</a> and map to its `.availabilityDate`

```xml
<efac:FieldsPrivacy>
  <efbc:PublicationDate>2025-03-31+01:00</efbc:PublicationDate>
</efac:FieldsPrivacy>
```

```json
{
  "withheldInformation": [
    {
      "availabilityDate": "2025-03-31T00:00:00+01:00"
    }
  ]
}
```

</td>
      </tr>
      <tr id="BT-198(BT-105)-Procedure">
        <td class="field break-all">
            <p><b>BT-198(BT-105)-Procedure</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/withheld-publication.html#procedureLevelSection"></a><br>Unpublished Access Date</p><p><i>BT-198:</i> The later date at which the originally unpublished field shall be published.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:TenderingProcess/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:FieldsPrivacy[efbc:FieldIdentifierCode/text()='pro-typ']/efbc:PublicationDate</span></code>
        </td>
        <td class="mapping">

Get the `withheldInformationItem` object created for BT-195(BT-105)-Procedure. <a href="operations.md#convert-a-date-to-iso-format">Convert date to ISO format</a> and map to its `.availabilityDate`

```xml
<efac:FieldsPrivacy>
  <efbc:PublicationDate>2025-03-31+01:00</efbc:PublicationDate>
</efac:FieldsPrivacy>
```

```json
{
  "withheldInformation": [
    {
      "availabilityDate": "2025-03-31T00:00:00+01:00"
    }
  ]
}
```

</td>
      </tr>
      <tr id="BT-198(BT-106)-Procedure">
        <td class="field break-all">
            <p><b>BT-198(BT-106)-Procedure</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/withheld-publication.html#procedureLevelSection"></a><br>Unpublished Access Date</p><p><i>BT-198:</i> The later date at which the originally unpublished field shall be published.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:TenderingProcess/cac:ProcessJustification[cbc:ProcessReasonCode/@listName='accelerated-procedure']/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:FieldsPrivacy[efbc:FieldIdentifierCode/text()='pro-acc']/efbc:PublicationDate</span></code>
        </td>
        <td class="mapping">

Get the `withheldInformationItem` object created for BT-195(BT-106)-Procedure. <a href="operations.md#convert-a-date-to-iso-format">Convert date to ISO format</a> and map to its `.availabilityDate`

```xml
<efac:FieldsPrivacy>
  <efbc:PublicationDate>2025-03-31+01:00</efbc:PublicationDate>
</efac:FieldsPrivacy>
```

```json
{
  "withheldInformation": [
    {
      "availabilityDate": "2025-03-31T00:00:00+01:00"
    }
  ]
}
```

</td>
      </tr>
      <tr id="BT-198(BT-1118)-NoticeResult">
        <td class="field break-all">
            <p><b>BT-198(BT-1118)-NoticeResult</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/withheld-publication.html#_notice_result_level"></a><br>Unpublished Access Date</p><p><i>BT-198:</i> The later date at which the originally unpublished field shall be published.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:NoticeResult/efac:FieldsPrivacy[efbc:FieldIdentifierCode/text()='not-app-val']/efbc:PublicationDate</span></code>
        </td>
        <td class="mapping">

Discard.

```xml
<efac:FieldsPrivacy>
  <efbc:PublicationDate>2025-03-31+01:00</efbc:PublicationDate>
</efac:FieldsPrivacy>
```



</td>
      </tr>
      <tr id="BT-198(BT-118)-NoticeResult">
        <td class="field break-all">
            <p><b>BT-198(BT-118)-NoticeResult</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/withheld-publication.html#_notice_result_level"></a><br>Unpublished Access Date</p><p><i>BT-198:</i> The later date at which the originally unpublished field shall be published.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:NoticeResult/efac:FieldsPrivacy[efbc:FieldIdentifierCode/text()='not-max-val']/efbc:PublicationDate</span></code>
        </td>
        <td class="mapping">

Discard.

```xml
<efac:FieldsPrivacy>
  <efbc:PublicationDate>2025-03-31+01:00</efbc:PublicationDate>
</efac:FieldsPrivacy>
```



</td>
      </tr>
      <tr id="BT-198(BT-1252)-Procedure">
        <td class="field break-all">
            <p><b>BT-198(BT-1252)-Procedure</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/withheld-publication.html#procedureLevelSection"></a><br>Unpublished Access Date</p><p><i>BT-198:</i> The later date at which the originally unpublished field shall be published.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:TenderingProcess/cac:ProcessJustification[cbc:ProcessReasonCode/@listName='direct-award-justification']/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:FieldsPrivacy[efbc:FieldIdentifierCode/text()='dir-awa-pre']/efbc:PublicationDate</span></code>
        </td>
        <td class="mapping">

Get the `withheldInformationItem` object created for BT-195(BT-1252)-Procedure. <a href="operations.md#convert-a-date-to-iso-format">Convert date to ISO format</a> and map to its `.availabilityDate`

```xml
<efac:FieldsPrivacy>
  <efbc:PublicationDate>2025-03-31+01:00</efbc:PublicationDate>
</efac:FieldsPrivacy>
```

```json
{
  "withheldInformation": [
    {
      "availabilityDate": "2025-03-31T00:00:00+01:00"
    }
  ]
}
```

</td>
      </tr>
      <tr id="BT-198(BT-135)-Procedure">
        <td class="field break-all">
            <p><b>BT-198(BT-135)-Procedure</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/withheld-publication.html#procedureLevelSection"></a><br>Unpublished Access Date</p><p><i>BT-198:</i> The later date at which the originally unpublished field shall be published.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:TenderingProcess/cac:ProcessJustification[cbc:ProcessReasonCode/@listName='direct-award-justification']/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:FieldsPrivacy[efbc:FieldIdentifierCode/text()='dir-awa-tex']/efbc:PublicationDate</span></code>
        </td>
        <td class="mapping">

Get the `withheldInformationItem` object created for BT-195(BT-135)-Procedure. <a href="operations.md#convert-a-date-to-iso-format">Convert date to ISO format</a> and map to its `.availabilityDate`

```xml
<efac:FieldsPrivacy>
  <efbc:PublicationDate>2025-03-31+01:00</efbc:PublicationDate>
</efac:FieldsPrivacy>
```

```json
{
  "withheldInformation": [
    {
      "availabilityDate": "2025-03-31T00:00:00+01:00"
    }
  ]
}
```

</td>
      </tr>
      <tr id="BT-198(BT-1351)-Procedure">
        <td class="field break-all">
            <p><b>BT-198(BT-1351)-Procedure</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/withheld-publication.html#procedureLevelSection"></a><br>Unpublished Access Date</p><p><i>BT-198:</i> The later date at which the originally unpublished field shall be published.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:TenderingProcess/cac:ProcessJustification[cbc:ProcessReasonCode/@listName='accelerated-procedure']/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:FieldsPrivacy[efbc:FieldIdentifierCode/text()='pro-acc-jus']/efbc:PublicationDate</span></code>
        </td>
        <td class="mapping">

Get the `withheldInformationItem` object created for BT-195(BT-1351)-Procedure. <a href="operations.md#convert-a-date-to-iso-format">Convert date to ISO format</a> and map to its `.availabilityDate`

```xml
<efac:FieldsPrivacy>
  <efbc:PublicationDate>2025-03-31+01:00</efbc:PublicationDate>
</efac:FieldsPrivacy>
```

```json
{
  "withheldInformation": [
    {
      "availabilityDate": "2025-03-31T00:00:00+01:00"
    }
  ]
}
```

</td>
      </tr>
      <tr id="BT-198(BT-136)-Procedure">
        <td class="field break-all">
            <p><b>BT-198(BT-136)-Procedure</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/withheld-publication.html#procedureLevelSection"></a><br>Unpublished Access Date</p><p><i>BT-198:</i> The later date at which the originally unpublished field shall be published.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:TenderingProcess/cac:ProcessJustification[cbc:ProcessReasonCode/@listName='direct-award-justification']/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:FieldsPrivacy[efbc:FieldIdentifierCode/text()='dir-awa-jus']/efbc:PublicationDate</span></code>
        </td>
        <td class="mapping">

Get the `withheldInformationItem` object created for BT-195(BT-136)-Procedure. <a href="operations.md#convert-a-date-to-iso-format">Convert date to ISO format</a> and map to its `.availabilityDate`

```xml
<efac:FieldsPrivacy>
  <efbc:PublicationDate>2025-03-31+01:00</efbc:PublicationDate>
</efac:FieldsPrivacy>
```

```json
{
  "withheldInformation": [
    {
      "availabilityDate": "2025-03-31T00:00:00+01:00"
    }
  ]
}
```

</td>
      </tr>
      <tr id="BT-198(BT-142)-LotResult">
        <td class="field break-all">
            <p><b>BT-198(BT-142)-LotResult</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/withheld-publication.html#lotResultLevelSection"></a><br>Unpublished Access Date</p><p><i>BT-198:</i> The later date at which the originally unpublished field shall be published.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:NoticeResult/efac:LotResult/efac:FieldsPrivacy[efbc:FieldIdentifierCode/text()='win-cho']/efbc:PublicationDate</span></code>
        </td>
        <td class="mapping">

Get the `withheldInformationItem` object created for BT-195(BT-142)-LotResult and `ancestor::efac:LotResult`. <a href="operations.md#convert-a-date-to-iso-format">Convert date to ISO format</a> and map to its `.availabilityDate`

```xml
<efac:FieldsPrivacy>
  <efbc:PublicationDate>2025-03-31+01:00</efbc:PublicationDate>
</efac:FieldsPrivacy>
```

```json
{
  "withheldInformation": [
    {
      "availabilityDate": "2025-03-31T00:00:00+01:00"
    }
  ]
}
```

</td>
      </tr>
      <tr id="BT-198(BT-144)-LotResult">
        <td class="field break-all">
            <p><b>BT-198(BT-144)-LotResult</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/withheld-publication.html#lotResultLevelSection"></a><br>Unpublished Access Date</p><p><i>BT-198:</i> The later date at which the originally unpublished field shall be published.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:NoticeResult/efac:LotResult/efac:DecisionReason/efac:FieldsPrivacy[efbc:FieldIdentifierCode/text()='no-awa-rea']/efbc:PublicationDate</span></code>
        </td>
        <td class="mapping">

Get the `withheldInformationItem` object created for BT-195(BT-144)-LotResult and `ancestor::efac:LotResult`. <a href="operations.md#convert-a-date-to-iso-format">Convert date to ISO format</a> and map to its `.availabilityDate`

```xml
<efac:FieldsPrivacy>
  <efbc:PublicationDate>2025-03-31+01:00</efbc:PublicationDate>
</efac:FieldsPrivacy>
```

```json
{
  "withheldInformation": [
    {
      "availabilityDate": "2025-03-31T00:00:00+01:00"
    }
  ]
}
```

</td>
      </tr>
      <tr id="BT-198(BT-156)-NoticeResult">
        <td class="field break-all">
            <p><b>BT-198(BT-156)-NoticeResult</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/withheld-publication.html#_notice_result_level"></a><br>Unpublished Access Date</p><p><i>BT-198:</i> The later date at which the originally unpublished field shall be published.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:NoticeResult/efac:GroupFramework/efac:FieldsPrivacy[efbc:FieldIdentifierCode/text()='gro-max-val']/efbc:PublicationDate</span></code>
        </td>
        <td class="mapping">

Discard.

```xml
<efac:FieldsPrivacy>
  <efbc:PublicationDate>2025-03-31+01:00</efbc:PublicationDate>
</efac:FieldsPrivacy>
```



</td>
      </tr>
      <tr id="BT-198(BT-1561)-NoticeResult">
        <td class="field break-all">
            <p><b>BT-198(BT-1561)-NoticeResult</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/withheld-publication.html#_notice_result_level"></a><br>Unpublished Access Date</p><p><i>BT-198:</i> The later date at which the originally unpublished field shall be published.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:NoticeResult/efac:GroupFramework/efac:FieldsPrivacy[efbc:FieldIdentifierCode/text()='not-ree-val']/efbc:PublicationDate</span></code>
        </td>
        <td class="mapping">

Discard.

```xml
<efac:FieldsPrivacy>
  <efbc:PublicationDate>2025-03-31+01:00</efbc:PublicationDate>
</efac:FieldsPrivacy>
```



</td>
      </tr>
      <tr id="BT-198(BT-160)-Tender">
        <td class="field break-all">
            <p><b>BT-198(BT-160)-Tender</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/withheld-publication.html#lotTenderLevelSection"></a><br>Unpublished Access Date</p><p><i>BT-198:</i> The later date at which the originally unpublished field shall be published.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:NoticeResult/efac:LotTender/efac:ConcessionRevenue/efac:FieldsPrivacy[efbc:FieldIdentifierCode/text()='con-rev-buy']/efbc:PublicationDate</span></code>
        </td>
        <td class="mapping">

Get the `withheldInformationItem` object created for BT-195(BT-160)-Tender and `ancestor::efac:LotTender`. <a href="operations.md#convert-a-date-to-iso-format">Convert date to ISO format</a> and map to its `.availabilityDate`

```xml
<efac:FieldsPrivacy>
  <efbc:PublicationDate>2025-03-31+01:00</efbc:PublicationDate>
</efac:FieldsPrivacy>
```

```json
{
  "withheldInformation": [
    {
      "availabilityDate": "2025-03-31T00:00:00+01:00"
    }
  ]
}
```

</td>
      </tr>
      <tr id="BT-198(BT-161)-NoticeResult">
        <td class="field break-all">
            <p><b>BT-198(BT-161)-NoticeResult</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/withheld-publication.html#_notice_result_level"></a><br>Unpublished Access Date</p><p><i>BT-198:</i> The later date at which the originally unpublished field shall be published.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:NoticeResult/efac:FieldsPrivacy[efbc:FieldIdentifierCode/text()='not-val']/efbc:PublicationDate</span></code>
        </td>
        <td class="mapping">

Discard.

```xml
<efac:FieldsPrivacy>
  <efbc:PublicationDate>2025-03-31+01:00</efbc:PublicationDate>
</efac:FieldsPrivacy>
```



</td>
      </tr>
      <tr id="BT-198(BT-162)-Tender">
        <td class="field break-all">
            <p><b>BT-198(BT-162)-Tender</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/withheld-publication.html#lotTenderLevelSection"></a><br>Unpublished Access Date</p><p><i>BT-198:</i> The later date at which the originally unpublished field shall be published.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:NoticeResult/efac:LotTender/efac:ConcessionRevenue/efac:FieldsPrivacy[efbc:FieldIdentifierCode/text()='con-rev-use']/efbc:PublicationDate</span></code>
        </td>
        <td class="mapping">

Get the `withheldInformationItem` object created for BT-195(BT-162)-Tender and `ancestor::efac:LotTender`. <a href="operations.md#convert-a-date-to-iso-format">Convert date to ISO format</a> and map to its `.availabilityDate`

```xml
<efac:FieldsPrivacy>
  <efbc:PublicationDate>2025-03-31+01:00</efbc:PublicationDate>
</efac:FieldsPrivacy>
```

```json
{
  "withheldInformation": [
    {
      "availabilityDate": "2025-03-31T00:00:00+01:00"
    }
  ]
}
```

</td>
      </tr>
      <tr id="BT-198(BT-163)-Tender">
        <td class="field break-all">
            <p><b>BT-198(BT-163)-Tender</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/withheld-publication.html#lotTenderLevelSection"></a><br>Unpublished Access Date</p><p><i>BT-198:</i> The later date at which the originally unpublished field shall be published.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:NoticeResult/efac:LotTender/efac:ConcessionRevenue/efac:FieldsPrivacy[efbc:FieldIdentifierCode/text()='val-con-des']/efbc:PublicationDate</span></code>
        </td>
        <td class="mapping">

Get the `withheldInformationItem` object created for BT-195(BT-163)-Tender and `ancestor::efac:LotTender`. <a href="operations.md#convert-a-date-to-iso-format">Convert date to ISO format</a> and map to its `.availabilityDate`

```xml
<efac:FieldsPrivacy>
  <efbc:PublicationDate>2025-03-31+01:00</efbc:PublicationDate>
</efac:FieldsPrivacy>
```

```json
{
  "withheldInformation": [
    {
      "availabilityDate": "2025-03-31T00:00:00+01:00"
    }
  ]
}
```

</td>
      </tr>
      <tr id="BT-198(BT-171)-Tender">
        <td class="field break-all">
            <p><b>BT-198(BT-171)-Tender</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/withheld-publication.html#lotTenderLevelSection"></a><br>Unpublished Access Date</p><p><i>BT-198:</i> The later date at which the originally unpublished field shall be published.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:NoticeResult/efac:LotTender/efac:FieldsPrivacy[efbc:FieldIdentifierCode/text()='ten-ran']/efbc:PublicationDate</span></code>
        </td>
        <td class="mapping">

Get the `withheldInformationItem` object created for BT-195(BT-171)-Tender and `ancestor::efac:LotTender`. <a href="operations.md#convert-a-date-to-iso-format">Convert date to ISO format</a> and map to its `.availabilityDate`

```xml
<efac:FieldsPrivacy>
  <efbc:PublicationDate>2025-03-31+01:00</efbc:PublicationDate>
</efac:FieldsPrivacy>
```

```json
{
  "withheldInformation": [
    {
      "availabilityDate": "2025-03-31T00:00:00+01:00"
    }
  ]
}
```

</td>
      </tr>
      <tr id="BT-198(BT-191)-Tender">
        <td class="field break-all">
            <p><b>BT-198(BT-191)-Tender</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/withheld-publication.html#lotTenderLevelSection"></a><br>Unpublished Access Date</p><p><i>BT-198:</i> The later date at which the originally unpublished field shall be published.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:NoticeResult/efac:LotTender/efac:Origin/efac:FieldsPrivacy[efbc:FieldIdentifierCode/text()='cou-ori']/efbc:PublicationDate</span></code>
        </td>
        <td class="mapping">

Get the `withheldInformationItem` object created for BT-195(BT-191)-Tender and `ancestor::efac:LotTender`. <a href="operations.md#convert-a-date-to-iso-format">Convert date to ISO format</a> and map to its `.availabilityDate`

```xml
<efac:FieldsPrivacy>
  <efbc:PublicationDate>2025-03-31+01:00</efbc:PublicationDate>
</efac:FieldsPrivacy>
```

```json
{
  "withheldInformation": [
    {
      "availabilityDate": "2025-03-31T00:00:00+01:00"
    }
  ]
}
```

</td>
      </tr>
      <tr id="BT-198(BT-193)-Tender">
        <td class="field break-all">
            <p><b>BT-198(BT-193)-Tender</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/withheld-publication.html#lotTenderLevelSection"></a><br>Unpublished Access Date</p><p><i>BT-198:</i> The later date at which the originally unpublished field shall be published.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:NoticeResult/efac:LotTender/efac:FieldsPrivacy[efbc:FieldIdentifierCode/text()='win-ten-var']/efbc:PublicationDate</span></code>
        </td>
        <td class="mapping">

Get the `withheldInformationItem` object created for BT-195(BT-193)-Tender and `ancestor::efac:LotTender`. <a href="operations.md#convert-a-date-to-iso-format">Convert date to ISO format</a> and map to its `.availabilityDate`

```xml
<efac:FieldsPrivacy>
  <efbc:PublicationDate>2025-03-31+01:00</efbc:PublicationDate>
</efac:FieldsPrivacy>
```

```json
{
  "withheldInformation": [
    {
      "availabilityDate": "2025-03-31T00:00:00+01:00"
    }
  ]
}
```

</td>
      </tr>
      <tr id="BT-198(BT-539)-Lot">
        <td class="field break-all">
            <p><b>BT-198(BT-539)-Lot</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/withheld-publication.html#lotsGroupOfLotsLevelSection"></a><br>Unpublished Access Date</p><p><i>BT-198:</i> The later date at which the originally unpublished field shall be published.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='Lot']/cac:TenderingTerms/cac:AwardingTerms/cac:AwardingCriterion/cac:SubordinateAwardingCriterion/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:FieldsPrivacy[efbc:FieldIdentifierCode/text()='awa-cri-typ']/efbc:PublicationDate</span></code>
        </td>
        <td class="mapping">

Get the `withheldInformationItem` object created for BT-195(BT-539)-Lot and `ancestor::cac:ProcurementProjectLot[cbc:ID schemeName="Lot"]`. <a href="operations.md#convert-a-date-to-iso-format">Convert date to ISO format</a> and map to its `.availabilityDate`

```xml
<efac:FieldsPrivacy>
  <efbc:PublicationDate>2025-03-31+01:00</efbc:PublicationDate>
</efac:FieldsPrivacy>
```

```json
{
  "withheldInformation": [
    {
      "availabilityDate": "2025-03-31T00:00:00+01:00"
    }
  ]
}
```

</td>
      </tr>
      <tr id="BT-198(BT-539)-LotsGroup">
        <td class="field break-all">
            <p><b>BT-198(BT-539)-LotsGroup</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/withheld-publication.html#lotsGroupOfLotsLevelSection"></a><br>Unpublished Access Date</p><p><i>BT-198:</i> The later date at which the originally unpublished field shall be published.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='LotsGroup']/cac:TenderingTerms/cac:AwardingTerms/cac:AwardingCriterion/cac:SubordinateAwardingCriterion/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:FieldsPrivacy[efbc:FieldIdentifierCode/text()='awa-cri-typ']/efbc:PublicationDate</span></code>
        </td>
        <td class="mapping">

Get the `withheldInformationItem` object created for BT-195(BT-539)-LotsGroup and `ancestor::cac:ProcurementProjectLot[cbc:ID schemeName="LotsGroup"]`. <a href="operations.md#convert-a-date-to-iso-format">Convert date to ISO format</a> and map to its `.availabilityDate`

```xml
<efac:FieldsPrivacy>
  <efbc:PublicationDate>2025-03-31+01:00</efbc:PublicationDate>
</efac:FieldsPrivacy>
```

```json
{
  "withheldInformation": [
    {
      "availabilityDate": "2025-03-31T00:00:00+01:00"
    }
  ]
}
```

</td>
      </tr>
      <tr id="BT-198(BT-540)-Lot">
        <td class="field break-all">
            <p><b>BT-198(BT-540)-Lot</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/withheld-publication.html#lotsGroupOfLotsLevelSection"></a><br>Unpublished Access Date</p><p><i>BT-198:</i> The later date at which the originally unpublished field shall be published.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='Lot']/cac:TenderingTerms/cac:AwardingTerms/cac:AwardingCriterion/cac:SubordinateAwardingCriterion/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:FieldsPrivacy[efbc:FieldIdentifierCode/text()='awa-cri-des']/efbc:PublicationDate</span></code>
        </td>
        <td class="mapping">

Get the `withheldInformationItem` object created for BT-195(BT-540)-Lot and `ancestor::cac:ProcurementProjectLot[cbc:ID schemeName="Lot"]`. <a href="operations.md#convert-a-date-to-iso-format">Convert date to ISO format</a> and map to its `.availabilityDate`

```xml
<efac:FieldsPrivacy>
  <efbc:PublicationDate>2025-03-31+01:00</efbc:PublicationDate>
</efac:FieldsPrivacy>
```

```json
{
  "withheldInformation": [
    {
      "availabilityDate": "2025-03-31T00:00:00+01:00"
    }
  ]
}
```

</td>
      </tr>
      <tr id="BT-198(BT-540)-LotsGroup">
        <td class="field break-all">
            <p><b>BT-198(BT-540)-LotsGroup</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/withheld-publication.html#lotsGroupOfLotsLevelSection"></a><br>Unpublished Access Date</p><p><i>BT-198:</i> The later date at which the originally unpublished field shall be published.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='LotsGroup']/cac:TenderingTerms/cac:AwardingTerms/cac:AwardingCriterion/cac:SubordinateAwardingCriterion/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:FieldsPrivacy[efbc:FieldIdentifierCode/text()='awa-cri-des']/efbc:PublicationDate</span></code>
        </td>
        <td class="mapping">

Get the `withheldInformationItem` object created for BT-195(BT-540)-LotsGroup and `ancestor::cac:ProcurementProjectLot[cbc:ID schemeName="LotsGroup"]`. <a href="operations.md#convert-a-date-to-iso-format">Convert date to ISO format</a> and map to its `.availabilityDate`

```xml
<efac:FieldsPrivacy>
  <efbc:PublicationDate>2025-03-31+01:00</efbc:PublicationDate>
</efac:FieldsPrivacy>
```

```json
{
  "withheldInformation": [
    {
      "availabilityDate": "2025-03-31T00:00:00+01:00"
    }
  ]
}
```

</td>
      </tr>
      <tr id="BT-198(BT-541)-Lot">
        <td class="field break-all">
            <p><b>BT-198(BT-541)-Lot</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/withheld-publication.html#lotsGroupOfLotsLevelSection"></a><br>Unpublished Access Date</p><p><i>BT-198:</i> The later date at which the originally unpublished field shall be published.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='Lot']/cac:TenderingTerms/cac:AwardingTerms/cac:AwardingCriterion/cac:SubordinateAwardingCriterion/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:AwardCriterionParameter/efac:FieldsPrivacy[efbc:FieldIdentifierCode/text()='awa-cri-num']/efbc:PublicationDate</span></code>
        </td>
        <td class="mapping">

Get the `withheldInformationItem` object created for BT-195(BT-541)-Lot and `ancestor::cac:ProcurementProjectLot[cbc:ID schemeName="Lot"]`. <a href="operations.md#convert-a-date-to-iso-format">Convert date to ISO format</a> and map to its `.availabilityDate`

```xml
<efac:FieldsPrivacy>
  <efbc:PublicationDate>2025-03-31+01:00</efbc:PublicationDate>
</efac:FieldsPrivacy>
```

```json
{
  "withheldInformation": [
    {
      "availabilityDate": "2025-03-31T00:00:00+01:00"
    }
  ]
}
```

</td>
      </tr>
      <tr id="BT-198(BT-541)-LotsGroup">
        <td class="field break-all">
            <p><b>BT-198(BT-541)-LotsGroup</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/withheld-publication.html#lotsGroupOfLotsLevelSection"></a><br>Unpublished Access Date</p><p><i>BT-198:</i> The later date at which the originally unpublished field shall be published.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='LotsGroup']/cac:TenderingTerms/cac:AwardingTerms/cac:AwardingCriterion/cac:SubordinateAwardingCriterion/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:AwardCriterionParameter/efac:FieldsPrivacy[efbc:FieldIdentifierCode/text()='awa-cri-num']/efbc:PublicationDate</span></code>
        </td>
        <td class="mapping">

Get the `withheldInformationItem` object created for BT-195(BT-541)-LotsGroup and `ancestor::cac:ProcurementProjectLot[cbc:ID schemeName="LotsGroup"]`. <a href="operations.md#convert-a-date-to-iso-format">Convert date to ISO format</a> and map to its `.availabilityDate`

```xml
<efac:FieldsPrivacy>
  <efbc:PublicationDate>2025-03-31+01:00</efbc:PublicationDate>
</efac:FieldsPrivacy>
```

```json
{
  "withheldInformation": [
    {
      "availabilityDate": "2025-03-31T00:00:00+01:00"
    }
  ]
}
```

</td>
      </tr>
      <tr id="BT-198(BT-5421)-Lot">
        <td class="field break-all">
            <p><b>BT-198(BT-5421)-Lot</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/withheld-publication.html#lotsGroupOfLotsLevelSection"></a><br>Unpublished Access Date</p><p><i>BT-198:</i> The later date at which the originally unpublished field shall be published.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='Lot']/cac:TenderingTerms/cac:AwardingTerms/cac:AwardingCriterion/cac:SubordinateAwardingCriterion/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:AwardCriterionParameter[efbc:ParameterCode/@listName='number-weight']/efac:FieldsPrivacy[efbc:FieldIdentifierCode/text()='awa-cri-wei']/efbc:PublicationDate</span></code>
        </td>
        <td class="mapping">

Get the `withheldInformationItem` object created for BT-195(BT-5421)-Lot and `ancestor::cac:ProcurementProjectLot[cbc:ID schemeName="Lot"]`. <a href="operations.md#convert-a-date-to-iso-format">Convert date to ISO format</a> and map to its `.availabilityDate`

```xml
<efac:FieldsPrivacy>
  <efbc:PublicationDate>2025-03-31+01:00</efbc:PublicationDate>
</efac:FieldsPrivacy>
```

```json
{
  "withheldInformation": [
    {
      "availabilityDate": "2025-03-31T00:00:00+01:00"
    }
  ]
}
```

</td>
      </tr>
      <tr id="BT-198(BT-5421)-LotsGroup">
        <td class="field break-all">
            <p><b>BT-198(BT-5421)-LotsGroup</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/withheld-publication.html#lotsGroupOfLotsLevelSection"></a><br>Unpublished Access Date</p><p><i>BT-198:</i> The later date at which the originally unpublished field shall be published.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='LotsGroup']/cac:TenderingTerms/cac:AwardingTerms/cac:AwardingCriterion/cac:SubordinateAwardingCriterion/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:AwardCriterionParameter[efbc:ParameterCode/@listName='number-weight']/efac:FieldsPrivacy[efbc:FieldIdentifierCode/text()='awa-cri-wei']/efbc:PublicationDate</span></code>
        </td>
        <td class="mapping">

Get the `withheldInformationItem` object created for BT-195(BT-5421)-LotsGroup and `ancestor::cac:ProcurementProjectLot[cbc:ID schemeName="LotsGroup"]`. <a href="operations.md#convert-a-date-to-iso-format">Convert date to ISO format</a> and map to its `.availabilityDate`

```xml
<efac:FieldsPrivacy>
  <efbc:PublicationDate>2025-03-31+01:00</efbc:PublicationDate>
</efac:FieldsPrivacy>
```

```json
{
  "withheldInformation": [
    {
      "availabilityDate": "2025-03-31T00:00:00+01:00"
    }
  ]
}
```

</td>
      </tr>
      <tr id="BT-198(BT-5422)-Lot">
        <td class="field break-all">
            <p><b>BT-198(BT-5422)-Lot</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/withheld-publication.html#lotsGroupOfLotsLevelSection"></a><br>Unpublished Access Date</p><p><i>BT-198:</i> The later date at which the originally unpublished field shall be published.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='Lot']/cac:TenderingTerms/cac:AwardingTerms/cac:AwardingCriterion/cac:SubordinateAwardingCriterion/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:AwardCriterionParameter[efbc:ParameterCode/@listName='number-fixed']/efac:FieldsPrivacy[efbc:FieldIdentifierCode/text()='awa-cri-fix']/efbc:PublicationDate</span></code>
        </td>
        <td class="mapping">

Get the `withheldInformationItem` object created for BT-195(BT-5422)-Lot and `ancestor::cac:ProcurementProjectLot[cbc:ID schemeName="Lot"]`. <a href="operations.md#convert-a-date-to-iso-format">Convert date to ISO format</a> and map to its `.availabilityDate`

```xml
<efac:FieldsPrivacy>
  <efbc:PublicationDate>2025-03-31+01:00</efbc:PublicationDate>
</efac:FieldsPrivacy>
```

```json
{
  "withheldInformation": [
    {
      "availabilityDate": "2025-03-31T00:00:00+01:00"
    }
  ]
}
```

</td>
      </tr>
      <tr id="BT-198(BT-5422)-LotsGroup">
        <td class="field break-all">
            <p><b>BT-198(BT-5422)-LotsGroup</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/withheld-publication.html#lotsGroupOfLotsLevelSection"></a><br>Unpublished Access Date</p><p><i>BT-198:</i> The later date at which the originally unpublished field shall be published.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='LotsGroup']/cac:TenderingTerms/cac:AwardingTerms/cac:AwardingCriterion/cac:SubordinateAwardingCriterion/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:AwardCriterionParameter[efbc:ParameterCode/@listName='number-fixed']/efac:FieldsPrivacy[efbc:FieldIdentifierCode/text()='awa-cri-fix']/efbc:PublicationDate</span></code>
        </td>
        <td class="mapping">

Get the `withheldInformationItem` object created for BT-195(BT-5422)-LotsGroup and `ancestor::cac:ProcurementProjectLot[cbc:ID schemeName="LotsGroup"]`. <a href="operations.md#convert-a-date-to-iso-format">Convert date to ISO format</a> and map to its `.availabilityDate`

```xml
<efac:FieldsPrivacy>
  <efbc:PublicationDate>2025-03-31+01:00</efbc:PublicationDate>
</efac:FieldsPrivacy>
```

```json
{
  "withheldInformation": [
    {
      "availabilityDate": "2025-03-31T00:00:00+01:00"
    }
  ]
}
```

</td>
      </tr>
      <tr id="BT-198(BT-5423)-Lot">
        <td class="field break-all">
            <p><b>BT-198(BT-5423)-Lot</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/withheld-publication.html#lotsGroupOfLotsLevelSection"></a><br>Unpublished Access Date</p><p><i>BT-198:</i> The later date at which the originally unpublished field shall be published.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='Lot']/cac:TenderingTerms/cac:AwardingTerms/cac:AwardingCriterion/cac:SubordinateAwardingCriterion/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:AwardCriterionParameter[efbc:ParameterCode/@listName='number-threshold']/efac:FieldsPrivacy[efbc:FieldIdentifierCode/text()='awa-cri-thr']/efbc:PublicationDate</span></code>
        </td>
        <td class="mapping">

Get the `withheldInformationItem` object created for BT-195(BT-5423)-Lot and `ancestor::cac:ProcurementProjectLot[cbc:ID schemeName="Lot"]`. <a href="operations.md#convert-a-date-to-iso-format">Convert date to ISO format</a> and map to its `.availabilityDate`

```xml
<efac:FieldsPrivacy>
  <efbc:PublicationDate>2025-03-31+01:00</efbc:PublicationDate>
</efac:FieldsPrivacy>
```

```json
{
  "withheldInformation": [
    {
      "availabilityDate": "2025-03-31T00:00:00+01:00"
    }
  ]
}
```

</td>
      </tr>
      <tr id="BT-198(BT-5423)-LotsGroup">
        <td class="field break-all">
            <p><b>BT-198(BT-5423)-LotsGroup</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/withheld-publication.html#lotsGroupOfLotsLevelSection"></a><br>Unpublished Access Date</p><p><i>BT-198:</i> The later date at which the originally unpublished field shall be published.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='LotsGroup']/cac:TenderingTerms/cac:AwardingTerms/cac:AwardingCriterion/cac:SubordinateAwardingCriterion/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:AwardCriterionParameter[efbc:ParameterCode/@listName='number-threshold']/efac:FieldsPrivacy[efbc:FieldIdentifierCode/text()='awa-cri-thr']/efbc:PublicationDate</span></code>
        </td>
        <td class="mapping">

Get the `withheldInformationItem` object created for BT-195(BT-5423)-LotsGroup and `ancestor::cac:ProcurementProjectLot[cbc:ID schemeName="LotsGroup"]`. <a href="operations.md#convert-a-date-to-iso-format">Convert date to ISO format</a> and map to its `.availabilityDate`

```xml
<efac:FieldsPrivacy>
  <efbc:PublicationDate>2025-03-31+01:00</efbc:PublicationDate>
</efac:FieldsPrivacy>
```

```json
{
  "withheldInformation": [
    {
      "availabilityDate": "2025-03-31T00:00:00+01:00"
    }
  ]
}
```

</td>
      </tr>
      <tr id="BT-198(BT-543)-Lot">
        <td class="field break-all">
            <p><b>BT-198(BT-543)-Lot</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/withheld-publication.html#lotsGroupOfLotsLevelSection"></a><br>Unpublished Access Date</p><p><i>BT-198:</i> The later date at which the originally unpublished field shall be published.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='Lot']/cac:TenderingTerms/cac:AwardingTerms/cac:AwardingCriterion/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:FieldsPrivacy[efbc:FieldIdentifierCode/text()='awa-cri-com']/efbc:PublicationDate</span></code>
        </td>
        <td class="mapping">

Get the `withheldInformationItem` object created for BT-195(BT-543)-Lot and `ancestor::cac:ProcurementProjectLot[cbc:ID schemeName="Lot"]`. <a href="operations.md#convert-a-date-to-iso-format">Convert date to ISO format</a> and map to its `.availabilityDate`

```xml
<efac:FieldsPrivacy>
  <efbc:PublicationDate>2025-03-31+01:00</efbc:PublicationDate>
</efac:FieldsPrivacy>
```

```json
{
  "withheldInformation": [
    {
      "availabilityDate": "2025-03-31T00:00:00+01:00"
    }
  ]
}
```

</td>
      </tr>
      <tr id="BT-198(BT-543)-LotsGroup">
        <td class="field break-all">
            <p><b>BT-198(BT-543)-LotsGroup</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/withheld-publication.html#lotsGroupOfLotsLevelSection"></a><br>Unpublished Access Date</p><p><i>BT-198:</i> The later date at which the originally unpublished field shall be published.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='LotsGroup']/cac:TenderingTerms/cac:AwardingTerms/cac:AwardingCriterion/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:FieldsPrivacy[efbc:FieldIdentifierCode/text()='awa-cri-com']/efbc:PublicationDate</span></code>
        </td>
        <td class="mapping">

Get the `withheldInformationItem` object created for BT-195(BT-543)-LotsGroup and `ancestor::cac:ProcurementProjectLot[cbc:ID schemeName="LotsGroup"]`. <a href="operations.md#convert-a-date-to-iso-format">Convert date to ISO format</a> and map to its `.availabilityDate`

```xml
<efac:FieldsPrivacy>
  <efbc:PublicationDate>2025-03-31+01:00</efbc:PublicationDate>
</efac:FieldsPrivacy>
```

```json
{
  "withheldInformation": [
    {
      "availabilityDate": "2025-03-31T00:00:00+01:00"
    }
  ]
}
```

</td>
      </tr>
      <tr id="BT-198(BT-553)-Tender">
        <td class="field break-all">
            <p><b>BT-198(BT-553)-Tender</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/withheld-publication.html#lotTenderLevelSection"></a><br>Unpublished Access Date</p><p><i>BT-198:</i> The later date at which the originally unpublished field shall be published.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:NoticeResult/efac:LotTender/efac:SubcontractingTerm/efac:FieldsPrivacy[efbc:FieldIdentifierCode/text()='sub-val']/efbc:PublicationDate</span></code>
        </td>
        <td class="mapping">

Get the `withheldInformationItem` object created for BT-195(BT-553)-Tender and `ancestor::efac:LotTender`. <a href="operations.md#convert-a-date-to-iso-format">Convert date to ISO format</a> and map to its `.availabilityDate`

```xml
<efac:FieldsPrivacy>
  <efbc:PublicationDate>2025-03-31+01:00</efbc:PublicationDate>
</efac:FieldsPrivacy>
```

```json
{
  "withheldInformation": [
    {
      "availabilityDate": "2025-03-31T00:00:00+01:00"
    }
  ]
}
```

</td>
      </tr>
      <tr id="BT-198(BT-554)-Tender">
        <td class="field break-all">
            <p><b>BT-198(BT-554)-Tender</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/withheld-publication.html#lotTenderLevelSection"></a><br>Unpublished Access Date</p><p><i>BT-198:</i> The later date at which the originally unpublished field shall be published.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:NoticeResult/efac:LotTender/efac:SubcontractingTerm/efac:FieldsPrivacy[efbc:FieldIdentifierCode/text()='sub-des']/efbc:PublicationDate</span></code>
        </td>
        <td class="mapping">

Get the `withheldInformationItem` object created for BT-195(BT-554)-Tender and `ancestor::efac:LotTender`. <a href="operations.md#convert-a-date-to-iso-format">Convert date to ISO format</a> and map to its `.availabilityDate`

```xml
<efac:FieldsPrivacy>
  <efbc:PublicationDate>2025-03-31+01:00</efbc:PublicationDate>
</efac:FieldsPrivacy>
```

```json
{
  "withheldInformation": [
    {
      "availabilityDate": "2025-03-31T00:00:00+01:00"
    }
  ]
}
```

</td>
      </tr>
      <tr id="BT-198(BT-555)-Tender">
        <td class="field break-all">
            <p><b>BT-198(BT-555)-Tender</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/withheld-publication.html#lotTenderLevelSection"></a><br>Unpublished Access Date</p><p><i>BT-198:</i> The later date at which the originally unpublished field shall be published.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:NoticeResult/efac:LotTender/efac:SubcontractingTerm/efac:FieldsPrivacy[efbc:FieldIdentifierCode/text()='sub-per']/efbc:PublicationDate</span></code>
        </td>
        <td class="mapping">

Get the `withheldInformationItem` object created for BT-195(BT-555)-Tender and `ancestor::efac:LotTender`. <a href="operations.md#convert-a-date-to-iso-format">Convert date to ISO format</a> and map to its `.availabilityDate`

```xml
<efac:FieldsPrivacy>
  <efbc:PublicationDate>2025-03-31+01:00</efbc:PublicationDate>
</efac:FieldsPrivacy>
```

```json
{
  "withheldInformation": [
    {
      "availabilityDate": "2025-03-31T00:00:00+01:00"
    }
  ]
}
```

</td>
      </tr>
      <tr id="BT-198(BT-556)-NoticeResult">
        <td class="field break-all">
            <p><b>BT-198(BT-556)-NoticeResult</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/withheld-publication.html#_notice_result_level"></a><br>Unpublished Access Date</p><p><i>BT-198:</i> The later date at which the originally unpublished field shall be published.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:NoticeResult/efac:GroupFramework/efac:FieldsPrivacy[efbc:FieldIdentifierCode/text()='gro-max-ide']/efbc:PublicationDate</span></code>
        </td>
        <td class="mapping">

Discard.

```xml
<efac:FieldsPrivacy>
  <efbc:PublicationDate>2025-03-31+01:00</efbc:PublicationDate>
</efac:FieldsPrivacy>
```



</td>
      </tr>
      <tr id="BT-198(BT-635)-LotResult">
        <td class="field break-all">
            <p><b>BT-198(BT-635)-LotResult</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/withheld-publication.html#lotResultLevelSection"></a><br>Unpublished Access Date</p><p><i>BT-198:</i> The later date at which the originally unpublished field shall be published.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:NoticeResult/efac:LotResult/efac:AppealRequestsStatistics[efbc:StatisticsCode/@listName='irregularity-type']/efac:FieldsPrivacy[efbc:FieldIdentifierCode/text()='buy-rev-cou']/efbc:PublicationDate</span></code>
        </td>
        <td class="mapping">

Get the `withheldInformationItem` object created for BT-195(BT-635)-LotResult and `ancestor::efac:LotResult`. <a href="operations.md#convert-a-date-to-iso-format">Convert date to ISO format</a> and map to its `.availabilityDate`

```xml
<efac:FieldsPrivacy>
  <efbc:PublicationDate>2025-03-31+01:00</efbc:PublicationDate>
</efac:FieldsPrivacy>
```

```json
{
  "withheldInformation": [
    {
      "availabilityDate": "2025-03-31T00:00:00+01:00"
    }
  ]
}
```

</td>
      </tr>
      <tr id="BT-198(BT-636)-LotResult">
        <td class="field break-all">
            <p><b>BT-198(BT-636)-LotResult</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/withheld-publication.html#lotResultLevelSection"></a><br>Unpublished Access Date</p><p><i>BT-198:</i> The later date at which the originally unpublished field shall be published.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:NoticeResult/efac:LotResult/efac:AppealRequestsStatistics[efbc:StatisticsCode/@listName='irregularity-type']/efac:FieldsPrivacy[efbc:FieldIdentifierCode/text()='buy-rev-typ']/efbc:PublicationDate</span></code>
        </td>
        <td class="mapping">

Get the `withheldInformationItem` object created for BT-195(BT-636)-LotResult and `ancestor::efac:LotResult`. <a href="operations.md#convert-a-date-to-iso-format">Convert date to ISO format</a> and map to its `.availabilityDate`

```xml
<efac:FieldsPrivacy>
  <efbc:PublicationDate>2025-03-31+01:00</efbc:PublicationDate>
</efac:FieldsPrivacy>
```

```json
{
  "withheldInformation": [
    {
      "availabilityDate": "2025-03-31T00:00:00+01:00"
    }
  ]
}
```

</td>
      </tr>
      <tr id="BT-198(BT-709)-LotResult">
        <td class="field break-all">
            <p><b>BT-198(BT-709)-LotResult</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/withheld-publication.html#lotResultLevelSection"></a><br>Unpublished Access Date</p><p><i>BT-198:</i> The later date at which the originally unpublished field shall be published.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:NoticeResult/efac:LotResult/efac:FrameworkAgreementValues/efac:FieldsPrivacy[efbc:FieldIdentifierCode/text()='max-val']/efbc:PublicationDate</span></code>
        </td>
        <td class="mapping">

Get the `withheldInformationItem` object created for BT-195(BT-709)-LotResult and `ancestor::efac:LotResult`. <a href="operations.md#convert-a-date-to-iso-format">Convert date to ISO format</a> and map to its `.availabilityDate`

```xml
<efac:FieldsPrivacy>
  <efbc:PublicationDate>2025-03-31+01:00</efbc:PublicationDate>
</efac:FieldsPrivacy>
```

```json
{
  "withheldInformation": [
    {
      "availabilityDate": "2025-03-31T00:00:00+01:00"
    }
  ]
}
```

</td>
      </tr>
      <tr id="BT-198(BT-710)-LotResult">
        <td class="field break-all">
            <p><b>BT-198(BT-710)-LotResult</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/withheld-publication.html#lotResultLevelSection"></a><br>Unpublished Access Date</p><p><i>BT-198:</i> The later date at which the originally unpublished field shall be published.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:NoticeResult/efac:LotResult/efac:FieldsPrivacy[efbc:FieldIdentifierCode/text()='ten-val-low']/efbc:PublicationDate</span></code>
        </td>
        <td class="mapping">

Get the `withheldInformationItem` object created for BT-195(BT-710)-LotResult and `ancestor::efac:LotResult`. <a href="operations.md#convert-a-date-to-iso-format">Convert date to ISO format</a> and map to its `.availabilityDate`

```xml
<efac:FieldsPrivacy>
  <efbc:PublicationDate>2025-03-31+01:00</efbc:PublicationDate>
</efac:FieldsPrivacy>
```

```json
{
  "withheldInformation": [
    {
      "availabilityDate": "2025-03-31T00:00:00+01:00"
    }
  ]
}
```

</td>
      </tr>
      <tr id="BT-198(BT-711)-LotResult">
        <td class="field break-all">
            <p><b>BT-198(BT-711)-LotResult</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/withheld-publication.html#lotResultLevelSection"></a><br>Unpublished Access Date</p><p><i>BT-198:</i> The later date at which the originally unpublished field shall be published.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:NoticeResult/efac:LotResult/efac:FieldsPrivacy[efbc:FieldIdentifierCode/text()='ten-val-hig']/efbc:PublicationDate</span></code>
        </td>
        <td class="mapping">

Get the `withheldInformationItem` object created for BT-195(BT-711)-LotResult and `ancestor::efac:LotResult`. <a href="operations.md#convert-a-date-to-iso-format">Convert date to ISO format</a> and map to its `.availabilityDate`

```xml
<efac:FieldsPrivacy>
  <efbc:PublicationDate>2025-03-31+01:00</efbc:PublicationDate>
</efac:FieldsPrivacy>
```

```json
{
  "withheldInformation": [
    {
      "availabilityDate": "2025-03-31T00:00:00+01:00"
    }
  ]
}
```

</td>
      </tr>
      <tr id="BT-198(BT-712)-LotResult">
        <td class="field break-all">
            <p><b>BT-198(BT-712)-LotResult</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/withheld-publication.html#lotResultLevelSection"></a><br>Unpublished Access Date</p><p><i>BT-198:</i> The later date at which the originally unpublished field shall be published.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:NoticeResult/efac:LotResult/efac:AppealRequestsStatistics[efbc:StatisticsCode/@listName='review-type']/efac:FieldsPrivacy[efbc:FieldIdentifierCode/text()='rev-req']/efbc:PublicationDate</span></code>
        </td>
        <td class="mapping">

Get the `withheldInformationItem` object created for BT-195(BT-712)-LotResult and `ancestor::efac:LotResult`. <a href="operations.md#convert-a-date-to-iso-format">Convert date to ISO format</a> and map to its `.availabilityDate`

```xml
<efac:FieldsPrivacy>
  <efbc:PublicationDate>2025-03-31+01:00</efbc:PublicationDate>
</efac:FieldsPrivacy>
```

```json
{
  "withheldInformation": [
    {
      "availabilityDate": "2025-03-31T00:00:00+01:00"
    }
  ]
}
```

</td>
      </tr>
      <tr id="BT-198(BT-720)-Tender">
        <td class="field break-all">
            <p><b>BT-198(BT-720)-Tender</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/withheld-publication.html#lotTenderLevelSection"></a><br>Unpublished Access Date</p><p><i>BT-198:</i> The later date at which the originally unpublished field shall be published.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:NoticeResult/efac:LotTender/efac:FieldsPrivacy[efbc:FieldIdentifierCode/text()='win-ten-val']/efbc:PublicationDate</span></code>
        </td>
        <td class="mapping">

Get the `withheldInformationItem` object created for BT-195(BT-720)-Tender and `ancestor::efac:LotTender`. <a href="operations.md#convert-a-date-to-iso-format">Convert date to ISO format</a> and map to its `.availabilityDate`

```xml
<efac:FieldsPrivacy>
  <efbc:PublicationDate>2025-03-31+01:00</efbc:PublicationDate>
</efac:FieldsPrivacy>
```

```json
{
  "withheldInformation": [
    {
      "availabilityDate": "2025-03-31T00:00:00+01:00"
    }
  ]
}
```

</td>
      </tr>
      <tr id="BT-198(BT-730)-Tender">
        <td class="field break-all">
            <p><b>BT-198(BT-730)-Tender</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/withheld-publication.html#lotTenderLevelSection"></a><br>Unpublished Access Date</p><p><i>BT-198:</i> The later date at which the originally unpublished field shall be published.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:NoticeResult/efac:LotTender/efac:SubcontractingTerm/efac:FieldsPrivacy[efbc:FieldIdentifierCode/text()='sub-val-kno']/efbc:PublicationDate</span></code>
        </td>
        <td class="mapping">

Discard. BT-730 is discarded as it is implied by BT-553.

```xml
<efac:FieldsPrivacy>
  <efbc:PublicationDate>2025-03-31+01:00</efbc:PublicationDate>
</efac:FieldsPrivacy>
```



</td>
      </tr>
      <tr id="BT-198(BT-731)-Tender">
        <td class="field break-all">
            <p><b>BT-198(BT-731)-Tender</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/withheld-publication.html#lotTenderLevelSection"></a><br>Unpublished Access Date</p><p><i>BT-198:</i> The later date at which the originally unpublished field shall be published.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:NoticeResult/efac:LotTender/efac:SubcontractingTerm/efac:FieldsPrivacy[efbc:FieldIdentifierCode/text()='sub-per-kno']/efbc:PublicationDate</span></code>
        </td>
        <td class="mapping">

Discard. BT-730 is discarded as it is implied by BT-553.

```xml
<efac:FieldsPrivacy>
  <efbc:PublicationDate>2025-03-31+01:00</efbc:PublicationDate>
</efac:FieldsPrivacy>
```



</td>
      </tr>
      <tr id="BT-198(BT-733)-Lot">
        <td class="field break-all">
            <p><b>BT-198(BT-733)-Lot</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/withheld-publication.html#lotsGroupOfLotsLevelSection"></a><br>Unpublished Access Date</p><p><i>BT-198:</i> The later date at which the originally unpublished field shall be published.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='Lot']/cac:TenderingTerms/cac:AwardingTerms/cac:AwardingCriterion/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:FieldsPrivacy[efbc:FieldIdentifierCode/text()='awa-cri-ord']/efbc:PublicationDate</span></code>
        </td>
        <td class="mapping">

Get the `withheldInformationItem` object created for BT-195(BT-733)-Lot and `ancestor::cac:ProcurementProjectLot[cbc:ID schemeName="Lot"]`. <a href="operations.md#convert-a-date-to-iso-format">Convert date to ISO format</a> and map to its `.availabilityDate`

```xml
<efac:FieldsPrivacy>
  <efbc:PublicationDate>2025-03-31+01:00</efbc:PublicationDate>
</efac:FieldsPrivacy>
```

```json
{
  "withheldInformation": [
    {
      "availabilityDate": "2025-03-31T00:00:00+01:00"
    }
  ]
}
```

</td>
      </tr>
      <tr id="BT-198(BT-733)-LotsGroup">
        <td class="field break-all">
            <p><b>BT-198(BT-733)-LotsGroup</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/withheld-publication.html#lotsGroupOfLotsLevelSection"></a><br>Unpublished Access Date</p><p><i>BT-198:</i> The later date at which the originally unpublished field shall be published.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='LotsGroup']/cac:TenderingTerms/cac:AwardingTerms/cac:AwardingCriterion/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:FieldsPrivacy[efbc:FieldIdentifierCode/text()='awa-cri-ord']/efbc:PublicationDate</span></code>
        </td>
        <td class="mapping">

Get the `withheldInformationItem` object created for BT-195(BT-733)-LotsGroup and `ancestor::cac:ProcurementProjectLot[cbc:ID schemeName="LotsGroup"]`. <a href="operations.md#convert-a-date-to-iso-format">Convert date to ISO format</a> and map to its `.availabilityDate`

```xml
"withheldInformation":[{"availabilityDate":"2025-03-31T00:00:00+01:00"}]
```

```json
{
  "withheldInformation": [
    {
      "availabilityDate": "2025-03-31T00:00:00+01:00"
    }
  ]
}
```

</td>
      </tr>
      <tr id="BT-198(BT-734)-Lot">
        <td class="field break-all">
            <p><b>BT-198(BT-734)-Lot</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/withheld-publication.html#lotsGroupOfLotsLevelSection"></a><br>Unpublished Access Date</p><p><i>BT-198:</i> The later date at which the originally unpublished field shall be published.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='Lot']/cac:TenderingTerms/cac:AwardingTerms/cac:AwardingCriterion/cac:SubordinateAwardingCriterion/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:FieldsPrivacy[efbc:FieldIdentifierCode/text()='awa-cri-nam']/efbc:PublicationDate</span></code>
        </td>
        <td class="mapping">

Get the `withheldInformationItem` object created for BT-195(BT-734)-Lot and `ancestor::cac:ProcurementProjectLot[cbc:ID schemeName="Lot"]`. <a href="operations.md#convert-a-date-to-iso-format">Convert date to ISO format</a> and map to its `.availabilityDate`

```xml
<efac:FieldsPrivacy>
  <efbc:PublicationDate>2025-03-31+01:00</efbc:PublicationDate>
</efac:FieldsPrivacy>
```

```json
{
  "withheldInformation": [
    {
      "availabilityDate": "2025-03-31T00:00:00+01:00"
    }
  ]
}
```

</td>
      </tr>
      <tr id="BT-198(BT-734)-LotsGroup">
        <td class="field break-all">
            <p><b>BT-198(BT-734)-LotsGroup</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/withheld-publication.html#lotsGroupOfLotsLevelSection"></a><br>Unpublished Access Date</p><p><i>BT-198:</i> The later date at which the originally unpublished field shall be published.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='LotsGroup']/cac:TenderingTerms/cac:AwardingTerms/cac:AwardingCriterion/cac:SubordinateAwardingCriterion/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:FieldsPrivacy[efbc:FieldIdentifierCode/text()='awa-cri-nam']/efbc:PublicationDate</span></code>
        </td>
        <td class="mapping">

Get the `withheldInformationItem` object created for BT-195(BT-734)-LotsGroup and `ancestor::cac:ProcurementProjectLot[cbc:ID schemeName="LotsGroup"]`. <a href="operations.md#convert-a-date-to-iso-format">Convert date to ISO format</a> and map to its `.availabilityDate`

```xml
<efac:FieldsPrivacy>
  <efbc:PublicationDate>2025-03-31+01:00</efbc:PublicationDate>
</efac:FieldsPrivacy>
```

```json
{
  "withheldInformation": [
    {
      "availabilityDate": "2025-03-31T00:00:00+01:00"
    }
  ]
}
```

</td>
      </tr>
      <tr id="BT-198(BT-759)-LotResult">
        <td class="field break-all">
            <p><b>BT-198(BT-759)-LotResult</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/withheld-publication.html#lotResultLevelSection"></a><br>Unpublished Access Date</p><p><i>BT-198:</i> The later date at which the originally unpublished field shall be published.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:NoticeResult/efac:LotResult/efac:ReceivedSubmissionsStatistics/efac:FieldsPrivacy[efbc:FieldIdentifierCode/text()='rec-sub-cou']/efbc:PublicationDate</span></code>
        </td>
        <td class="mapping">

Get the `withheldInformationItem` object created for BT-195(BT-759)-LotResult and `ancestor::efac:LotResult`. <a href="operations.md#convert-a-date-to-iso-format">Convert date to ISO format</a> and map to its `.availabilityDate`.

```xml
<efac:FieldsPrivacy>
  <efbc:PublicationDate>2025-03-31+01:00</efbc:PublicationDate>
</efac:FieldsPrivacy>
```

```json
{
  "withheldInformation": [
    {
      "availabilityDate": "2025-03-31T00:00:00+01:00"
    }
  ]
}
```

</td>
      </tr>
      <tr id="BT-198(BT-760)-LotResult">
        <td class="field break-all">
            <p><b>BT-198(BT-760)-LotResult</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/withheld-publication.html#lotResultLevelSection"></a><br>Unpublished Access Date</p><p><i>BT-198:</i> The later date at which the originally unpublished field shall be published.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:NoticeResult/efac:LotResult/efac:ReceivedSubmissionsStatistics/efac:FieldsPrivacy[efbc:FieldIdentifierCode/text()='rec-sub-typ']/efbc:PublicationDate</span></code>
        </td>
        <td class="mapping">

Get the `withheldInformationItem` object created for BT-195(BT-760)-LotResult and `ancestor::efac:LotResult`. <a href="operations.md#convert-a-date-to-iso-format">Convert date to ISO format</a> and map to its `.availabilityDate`.

```xml
<efac:FieldsPrivacy>
  <efbc:PublicationDate>2025-03-31+01:00</efbc:PublicationDate>
</efac:FieldsPrivacy>
```

```json
{
  "withheldInformation": [
    {
      "availabilityDate": "2025-03-31T00:00:00+01:00"
    }
  ]
}
```

</td>
      </tr>
      <tr id="BT-198(BT-773)-Tender">
        <td class="field break-all">
            <p><b>BT-198(BT-773)-Tender</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/withheld-publication.html#lotTenderLevelSection"></a><br>Unpublished Access Date</p><p><i>BT-198:</i> The later date at which the originally unpublished field shall be published.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:NoticeResult/efac:LotTender/efac:SubcontractingTerm/efac:FieldsPrivacy[efbc:FieldIdentifierCode/text()='sub-con']/efbc:PublicationDate</span></code>
        </td>
        <td class="mapping">

Get the `withheldInformationItem` object created for BT-195(BT-773)-Tender and `ancestor::efac:LotTender`. <a href="operations.md#convert-a-date-to-iso-format">Convert date to ISO format</a> and map to its `.availabilityDate`

```xml
<efac:FieldsPrivacy>
  <efbc:PublicationDate>2025-03-31+01:00</efbc:PublicationDate>
</efac:FieldsPrivacy>
```

```json
{
  "withheldInformation": [
    {
      "availabilityDate": "2025-03-31T00:00:00+01:00"
    }
  ]
}
```

</td>
      </tr>
      <tr id="BT-198(BT-88)-Procedure">
        <td class="field break-all">
            <p><b>BT-198(BT-88)-Procedure</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/withheld-publication.html#procedureLevelSection"></a><br>Unpublished Access Date</p><p><i>BT-198:</i> The later date at which the originally unpublished field shall be published.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:TenderingProcess/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:FieldsPrivacy[efbc:FieldIdentifierCode/text()='pro-fea']/efbc:PublicationDate</span></code>
        </td>
        <td class="mapping">

Get the `withheldInformationItem` object created for BT-195(BT-88)-Procedure. <a href="operations.md#convert-a-date-to-iso-format">Convert date to ISO format</a> and map to its `.availabilityDate`

```xml
<efac:FieldsPrivacy>
  <efbc:PublicationDate>2025-03-31+01:00</efbc:PublicationDate>
</efac:FieldsPrivacy>
```

```json
{
  "withheldInformation": [
    {
      "availabilityDate": "2025-03-31T00:00:00+01:00"
    }
  ]
}
```

</td>
      </tr>
      <tr id="BT-200-Contract">
        <td class="field break-all">
            <p><b>BT-200-Contract</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/contract-modification-notice.html"></a><br>Modification Reason Code</p><p><i>BT-200:</i> The main reason for modifying the contract.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:ContractModification/efac:ChangeReason/cbc:ReasonCode</span></code>
        </td>
        <td class="mapping">

This field maps to the same `Amendment` objects as created for BT-201-Contract and BT-202-Contract.

For each `efac:ChangeReason`, add or update a corresponding `Amendement` object to the contract's `.amendements` array ensuring its `.id` (string) is set. The `.id` can be any value guaranteed to be globally unique. For example, it can be set to a <a href="https://en.wikipedia.org/wiki/Universally_unique_identifier">version 4 UUID</a>, or it can be assigned sequentially across all notices for this procedure (the first notice sets it to "1", the second to "2", etc.).

Map to the amendment's `.rationaleClassifications.id`. Look up the code's label in the <a href="https://op.europa.eu/en/web/eu-vocabularies/dataset/-/resource?uri=http://publications.europa.eu/resource/dataset/modification-justification">authority table</a> and map it to `.rationaleClassifications.description` and set `.rationaleClassifications.scheme` to 'modification justification'.

```xml
<efac:ChangeReason>
  <cbc:ReasonCode listName="modification-justification">add-wss</cbc:ReasonCode>
</efac:ChangeReason>
```

```json
{
  "contracts": [
    {
      "amendments": [
        {
          "rationaleClassifications": [
            {
              "id": "add-wss",
              "description": "Need for additional works, services or supplies by the original contractor.",
              "scheme": "Modification justification"
            }
          ]
        }
      ]
    }
  ]
}
```

</td>
      </tr>
      <tr id="BT-201-Contract">
        <td class="field break-all">
            <p><b>BT-201-Contract</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/contract-modification-notice.html"></a><br>Modification Reason Description</p><p><i>BT-201:</i> The description of the main reason for modifying the contract.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:ContractModification/efac:ChangeReason/efbc:ReasonDescription</span></code>
        </td>
        <td class="mapping">

This field maps to the same `Amendment` objects as created for BT-200-Contract and BT-202-Contract.
For each `efac:ChangeReason`, add or update a corresponding `Amendement` object to the contract's `.amendements` array ensuring its `.id` (string) is set. The `.id` can be any value guaranteed to be globally unique. For example, it can be set to a <a href="https://en.wikipedia.org/wiki/Universally_unique_identifier">version 4 UUID</a>, or it can be assigned sequentially across all notices for this procedure (the first notice sets it to "1", the second to "2", etc.).
Map to the amendment's `.rationale`

```xml
<efac:ChangeReason>
  <efbc:ReasonDescription languageID="ENG">The original business case was scoped as a technology replacement programme for a single system. It was agreed that the organisation should consider people and process in addition to systems replacement, and work has been re-scoped to accommodate this.</efbc:ReasonDescription>
</efac:ChangeReason>
```

```json
{
  "contracts": [
    {
      "amendments": [
        {
          "rationale": "The original business case was scoped as a technology replacement programme for a single system. It was agreed that the organisation should consider people and process in addition to systems replacement, and work has been re-scoped to accommodate this."
        }
      ]
    }
  ]
}
```

</td>
      </tr>
      <tr id="BT-202-Contract">
        <td class="field break-all">
            <p><b>BT-202-Contract</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/contract-modification-notice.html"></a><br>Modification Description</p><p><i>BT-202:</i> The summary of the contract modification(s).</p>
            <code class="docutils literal notranslate"><span class="pre">/*/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:ContractModification/efac:Change/efbc:ChangeDescription</span></code>
        </td>
        <td class="mapping">

This field maps to the same `Amendment` objects as created for BT-200-Contract and BT-201-Contract.
For each `ancestor::efac:ContractModification/efac:ChangeReason`, add or update a corresponding `Amendement` object to the contract's `.amendements` array ensuring its `.id` (string) is set. The `.id` can be any value guaranteed to be globally unique. For example, it can be set to a <a href="https://en.wikipedia.org/wiki/Universally_unique_identifier">version 4 UUID</a>, or it can be assigned sequentially across all notices for this procedure (the first notice sets it to "1", the second to "2", etc.).
Map to the amendment's `.description`.

```xml
<efac:Change>
  <efbc:ChangeDescription languageID="ENG">Increase in framework value</efbc:ChangeDescription>
</efac:Change>
```

```json
{
  "contracts": [
    {
      "amendments": [
        {
          "description": "Increase in framework value."
        }
      ]
    }
  ]
}
```

</td>
      </tr>
      <tr id="BT-21-Lot">
        <td class="field break-all">
            <p><b>BT-21-Lot</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/procedure-lot-part-information.html#objectSection"></a><br>Title</p><p><i>BT-21:</i> The name of the procurement procedure or lot.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='Lot']/cac:ProcurementProject/cbc:Name</span></code>
        </td>
        <td class="mapping">

<a href="operations.md#get-the-lot-for-a-procurementprojectlot">Get the lot for the ProcurementProjectLot</a> and map to its `.title`.

```xml
<cbc:Name languageID="ENG">Computer Network extension</cbc:Name>
```

```json
{
  "tender": {
    "lots": [
      {
        "title": "Computer Network extension"
      }
    ]
  }
}
```

</td>
      </tr>
      <tr id="BT-21-LotsGroup">
        <td class="field break-all">
            <p><b>BT-21-LotsGroup</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/procedure-lot-part-information.html#objectSection"></a><br>Title</p><p><i>BT-21:</i> The name of the procurement procedure or lot.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='LotsGroup']/cac:ProcurementProject/cbc:Name</span></code>
        </td>
        <td class="mapping">

<a href="operations.md#get-the-lot-group-for-a-procurementprojectlot">Get the lot group for the ProcurementProjectLot</a> and map to its `.title`.

```xml
<cbc:Name languageID="ENG">Computer Network extension</cbc:Name>
```

```json
{
  "tender": {
    "lotGroups": [
      {
        "title": "Computer Network extension"
      }
    ]
  }
}
```

</td>
      </tr>
      <tr id="BT-21-Part">
        <td class="field break-all">
            <p><b>BT-21-Part</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/procedure-lot-part-information.html#objectSection"></a><br>Title</p><p><i>BT-21:</i> The name of the procurement procedure or lot.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='Part']/cac:ProcurementProject/cbc:Name</span></code>
        </td>
        <td class="mapping">

Map to `tender.title`

```xml
<cbc:Name languageID="ENG">Computer Network extension</cbc:Name>
```

```json
{
  "tender": {
    "title": "Computer Network extension"
  }
}
```

</td>
      </tr>
      <tr id="BT-21-Procedure">
        <td class="field break-all">
            <p><b>BT-21-Procedure</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/procedure-lot-part-information.html#objectSection"></a><br>Title</p><p><i>BT-21:</i> The name of the procurement procedure or lot.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProject/cbc:Name</span></code>
        </td>
        <td class="mapping">

Map to `tender.title`

```xml
<cbc:Name languageID="ENG">Computer Network extension</cbc:Name>
```

```json
{
  "tender": {
    "title": "Computer Network extension"
  }
}
```

</td>
      </tr>
      <tr id="BT-22-Lot">
        <td class="field break-all">
            <p><b>BT-22-Lot</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/procedure-lot-part-information.html#objectSection"></a><br>Internal Identifier</p><p><i>BT-22:</i> The internal identifier used for files regarding the procurement procedure or lot before a procedure identifier is given (e.g. coming from the buyer's document management system or procurement planning system). </p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='Lot']/cac:ProcurementProject/cbc:ID</span></code>
        </td>
        <td class="mapping">

<a href="operations.md#get-the-lot-for-a-procurementprojectlot">Get the lot for the ProcurementProjectLot</a> and map to its `.identifiers.id` and set `.identifiers.scheme` to "internal".

```xml
<cbc:ID schemeName="InternalID">PROC/2020/0024-ABC-FGHI</cbc:ID>
```

```json
{
  "tender": {
    "lots": [
      {
        "identifiers": [
          {
            "id": "PROC/2020/0024-ABC-FGHI",
            "scheme": "internal"
          }
        ]
      }
    ]
  }
}
```

</td>
      </tr>
      <tr id="BT-22-LotsGroup">
        <td class="field break-all">
            <p><b>BT-22-LotsGroup</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/procedure-lot-part-information.html#objectSection"></a><br>Internal Identifier</p><p><i>BT-22:</i> The internal identifier used for files regarding the procurement procedure or lot before a procedure identifier is given (e.g. coming from the buyer's document management system or procurement planning system). </p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='LotsGroup']/cac:ProcurementProject/cbc:ID</span></code>
        </td>
        <td class="mapping">

<a href="operations.md#get-the-lot-group-for-a-procurementprojectlot">Get the lot group for the ProcurementProjectLot</a> and map to its `.identifiers.id` and set `.identifiers.scheme` to "internal".

```xml
<cbc:ID schemeName="InternalID">PROC/2020/0024-ABC-FGHI</cbc:ID>
```

```json
{
  "tender": {
    "lotGroups": [
      {
        "identifiers": [
          {
            "id": "PROC/2020/0024-ABC-FGHI",
            "scheme": "internal"
          }
        ]
      }
    ]
  }
}
```

</td>
      </tr>
      <tr id="BT-22-Part">
        <td class="field break-all">
            <p><b>BT-22-Part</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/procedure-lot-part-information.html#objectSection"></a><br>Internal Identifier</p><p><i>BT-22:</i> The internal identifier used for files regarding the procurement procedure or lot before a procedure identifier is given (e.g. coming from the buyer's document management system or procurement planning system). </p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='Part']/cac:ProcurementProject/cbc:ID</span></code>
        </td>
        <td class="mapping">

Map to `tender.identifiers.id` and set `identifiers.scheme` to "internal".

```xml
<cbc:ID schemeName="InternalID">PROC/2020/0024-ABC-FGHI</cbc:ID>
```

```json
{
  "tender": {
    "identifiers": [
      {
        "id": "PROC/2020/0024-ABC-FGHI",
        "scheme": "internal"
      }
    ]
  }
}
```

</td>
      </tr>
      <tr id="BT-22-Procedure">
        <td class="field break-all">
            <p><b>BT-22-Procedure</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/procedure-lot-part-information.html#objectSection"></a><br>Internal Identifier</p><p><i>BT-22:</i> The internal identifier used for files regarding the procurement procedure or lot before a procedure identifier is given (e.g. coming from the buyer's document management system or procurement planning system). </p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProject/cbc:ID</span></code>
        </td>
        <td class="mapping">

Map to `tender.identifiers.id` and set `identifiers.scheme` to "internal".

```xml
<cbc:ID schemeName="InternalID">PROC/2020/0024-ABC-FGHI</cbc:ID>
```

```json
{
  "tender": {
    "identifiers": [
      {
        "id": "PROC/2020/0024-ABC-FGHI",
        "scheme": "internal"
      }
    ]
  }
}
```

</td>
      </tr>
      <tr id="BT-23-Lot">
        <td class="field break-all">
            <p><b>BT-23-Lot</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/procedure-lot-part-information.html#natureSection"></a><br>Main Nature</p><p><i>BT-23:</i> The main nature (e.g. works) of what is being bought. In case of mixed procurement (e.g. a procedure for both works and services), the main nature may be, for example, the one with the highest estimated value. This information shall be given for the whole procedure.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='Lot']/cac:ProcurementProject/cbc:ProcurementTypeCode[@listName='contract-nature']</span></code>
        </td>
        <td class="mapping">

<a href="operations.md#get-the-lot-for-a-procurementprojectlot">Get the lot for the ProcurementProjectLot</a>. If "works" or "services", map to the lot's `.mainProcurementCategory`. If "supplies", set the lot's `.mainProcurementCategory` to 'goods'. If "combined", add to the lot's `.additionalProcurementCategories` array.

```xml
<cbc:ProcurementTypeCode listName="contract-nature">works</cbc:ProcurementTypeCode>
```

```json
{
  "tender": {
    "lots": [
      {
        "mainProcurementCategory": "works"
      }
    ]
  }
}
```

</td>
      </tr>
      <tr id="BT-23-Part">
        <td class="field break-all">
            <p><b>BT-23-Part</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/procedure-lot-part-information.html#natureSection"></a><br>Main Nature</p><p><i>BT-23:</i> The main nature (e.g. works) of what is being bought. In case of mixed procurement (e.g. a procedure for both works and services), the main nature may be, for example, the one with the highest estimated value. This information shall be given for the whole procedure.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='Part']/cac:ProcurementProject/cbc:ProcurementTypeCode[@listName='contract-nature']</span></code>
        </td>
        <td class="mapping">

If "works" or "services", map to `tender.mainProcurementCategory`. If "supplies", set `tender.mainProcurementCategory` to 'goods'. If "combined", add to the `tender.additionalProcurementCategories` array.

```xml
<cbc:ProcurementTypeCode listName="contract-nature">works</cbc:ProcurementTypeCode>
```

```json
{
  "tender": {
    "mainProcurementCategory": "works"
  }
}
```

</td>
      </tr>
      <tr id="BT-23-Procedure">
        <td class="field break-all">
            <p><b>BT-23-Procedure</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/procedure-lot-part-information.html#natureSection"></a><br>Main Nature</p><p><i>BT-23:</i> The main nature (e.g. works) of what is being bought. In case of mixed procurement (e.g. a procedure for both works and services), the main nature may be, for example, the one with the highest estimated value. This information shall be given for the whole procedure.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProject/cbc:ProcurementTypeCode</span></code>
        </td>
        <td class="mapping">

If "works" or "services", map to `tender.mainProcurementCategory`. If "supplies", set `tender.mainProcurementCategory` to 'goods'. If "combined", add to the `tender.additionalProcurementCategories` array.

```xml
<cbc:ProcurementTypeCode listName="contract-nature">works</cbc:ProcurementTypeCode>
```

```json
{
  "tender": {
    "mainProcurementCategory": "works"
  }
}
```

</td>
      </tr>
      <tr id="BT-24-Lot">
        <td class="field break-all">
            <p><b>BT-24-Lot</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/procedure-lot-part-information.html#objectSection"></a><br>Description</p><p><i>BT-24:</i> The description of the nature and quantity of what is being bought or of the needs and requirements that shall be met in this procedure or lot. In case of a modification notice, the description of the procurement before and after the modification.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='Lot']/cac:ProcurementProject/cbc:Description</span></code>
        </td>
        <td class="mapping">

<a href="operations.md#get-the-lot-for-a-procurementprojectlot">Get the lot for the ProcurementProjectLot</a> and map to its `.description`.

```xml
<cbc:Description languageID="ENG">Procedure for the procurement of ...</cbc:Description>
```

```json
{
  "tender": {
    "lots": [
      {
        "description": "Procedure for the procurement of ..."
      }
    ]
  }
}
```

</td>
      </tr>
      <tr id="BT-24-LotsGroup">
        <td class="field break-all">
            <p><b>BT-24-LotsGroup</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/procedure-lot-part-information.html#objectSection"></a><br>Description</p><p><i>BT-24:</i> The description of the nature and quantity of what is being bought or of the needs and requirements that shall be met in this procedure or lot. In case of a modification notice, the description of the procurement before and after the modification.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='LotsGroup']/cac:ProcurementProject/cbc:Description</span></code>
        </td>
        <td class="mapping">

<a href="operations.md#get-the-lot-group-for-a-procurementprojectlot">Get the lot group for the ProcurementProjectLot</a> and map to its `.description`.

```xml
<cbc:Description languageID="ENG">Procedure for the procurement of ...</cbc:Description>
```

```json
{
  "tender": {
    "lotGroups": [
      {
        "description": "Procedure for the procurement of ..."
      }
    ]
  }
}
```

</td>
      </tr>
      <tr id="BT-24-Part">
        <td class="field break-all">
            <p><b>BT-24-Part</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/procedure-lot-part-information.html#objectSection"></a><br>Description</p><p><i>BT-24:</i> The description of the nature and quantity of what is being bought or of the needs and requirements that shall be met in this procedure or lot. In case of a modification notice, the description of the procurement before and after the modification.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='Part']/cac:ProcurementProject/cbc:Description</span></code>
        </td>
        <td class="mapping">

Map to `tender.description`.

```xml
<cbc:Description languageID="ENG">Procedure for the procurement of ...</cbc:Description>
```

```json
{
  "tender": {
    "description": "Procedure for the procurement of ..."
  }
}
```

</td>
      </tr>
      <tr id="BT-24-Procedure">
        <td class="field break-all">
            <p><b>BT-24-Procedure</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/procedure-lot-part-information.html#objectSection"></a><br>Description</p><p><i>BT-24:</i> The description of the nature and quantity of what is being bought or of the needs and requirements that shall be met in this procedure or lot. In case of a modification notice, the description of the procurement before and after the modification.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProject/cbc:Description</span></code>
        </td>
        <td class="mapping">

Map to `tender.description`.

```xml
<cbc:Description languageID="ENG">Procedure for the procurement of ...</cbc:Description>
```

```json
{
  "tender": {
    "description": "Procedure for the procurement of ..."
  }
}
```

</td>
      </tr>
      <tr id="BT-25-Lot">
        <td class="field break-all">
            <p><b>BT-25-Lot</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/procedure-lot-part-information.html#quantitySection"></a><br>Quantity</p><p><i>BT-25:</i> The number of units required.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='Lot']/cac:ProcurementProject/cbc:EstimatedOverallContractQuantity</span></code>
        </td>
        <td class="mapping">

<a href="operations.md#get-the-item-for-a-procurementprojectlot">Get the item for the ProcurementProjectLot</a>, map to its `.quantity`, and add the value of `ancestor::cac:ProcurementProjectLot/cac:ID` to its `.relatedLots`.

```xml
<cbc:EstimatedOverallContractQuantity unitCode="TNE">45000</cbc:EstimatedOverallContractQuantity>
```

```json
{
  "tender": {
    "items": [
      {
        "quantity": 45000,
        "relatedLots": [
          "LOT-0001"
        ]
      }
    ]
  }
}
```

</td>
      </tr>
      <tr id="BT-26(a)-Lot">
        <td class="field break-all">
            <p><b>BT-26(a)-Lot</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/procedure-lot-part-information.html#classificationSection"></a><br>Classification Type (e.g. CPV)</p><p><i>BT-26:</i> The type of classification describing the purchase (e.g. the CPV).</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='Lot']/cac:ProcurementProject/cac:AdditionalCommodityClassification/cbc:ItemClassificationCode/@listName</span></code>
        </td>
        <td class="mapping">

This field maps to the same objects as created for BT-263-Lot.

<a href="operations.md#get-the-item-for-a-procurementprojectlot">Get the item for the ProcurementProjectLot</a>. For each `cac:AdditionalCommodityClassification/cbc:ItemClassificationCode`, add or update a corresponding `Classification` object in the item's `.additionalClassifications` array, capitalize and map to the classification's `.scheme`.

```xml
<cac:AdditionalCommodityClassification>
  <cbc:ItemClassificationCode listName="cpv">15311200</cbc:ItemClassificationCode>
</cac:AdditionalCommodityClassification>
```

```json
{
  "tender": {
    "items": [
      {
        "additionalClassifications": [
          {
            "scheme": "CPV"
          }
        ],
        "relatedLots": [
          "LOT-0001"
        ]
      }
    ]
  }
}
```

</td>
      </tr>
      <tr id="BT-26(a)-Part">
        <td class="field break-all">
            <p><b>BT-26(a)-Part</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/procedure-lot-part-information.html#classificationSection"></a><br>Classification Type (e.g. CPV)</p><p><i>BT-26:</i> The type of classification describing the purchase (e.g. the CPV).</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='Part']/cac:ProcurementProject/cac:AdditionalCommodityClassification/cbc:ItemClassificationCode/@listName</span></code>
        </td>
        <td class="mapping">

This field maps to the same objects as created for BT-263-Part. If no `Item` objects were created for `ancestor::AdditionalCommodityClassification`:

- Add an `Item object to the `tender.items\` array.
- Set the item's `id` incrementally.
  For each `cac:AdditionalCommodityClassification/cbc:ItemClassificationCode`, add or update a corresponding `Classification` object in the item's `.additionalClassifications`, capitalize and map to the classification's `.scheme`.

```xml
<cac:AdditionalCommodityClassification>
  <cbc:ItemClassificationCode listName="cpv">15311200</cbc:ItemClassificationCode>
</cac:AdditionalCommodityClassification>
```

```json
{
  "tender": {
    "items": [
      {
        "additionalClassifications": [
          {
            "scheme": "CPV"
          }
        ]
      }
    ]
  }
}
```

</td>
      </tr>
      <tr id="BT-26(a)-Procedure">
        <td class="field break-all">
            <p><b>BT-26(a)-Procedure</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/procedure-lot-part-information.html#classificationSection"></a><br>Classification Type (e.g. CPV)</p><p><i>BT-26:</i> The type of classification describing the purchase (e.g. the CPV).</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProject/cac:AdditionalCommodityClassification/cbc:ItemClassificationCode/@listName</span></code>
        </td>
        <td class="mapping">

This field maps to the same objects as created for BT-263-Procedure. If no `Item` objects were created for `ancestor::AdditionalCommodityClassification`:

- Add an `Item object to the `tender.items\` array.
- Set the item's `id` incrementally.
  For each `cac:AdditionalCommodityClassification/cbc:ItemClassificationCode`, add or update a corresponding `Classification` object in the item's `.additionalClassifications`, capitalize and map to the classification's `.scheme`.

```xml
<cac:AdditionalCommodityClassification>
  <cbc:ItemClassificationCode listName="cpv">15311200</cbc:ItemClassificationCode>
</cac:AdditionalCommodityClassification>
```

```json
{
  "tender": {
    "items": [
      {
        "additionalClassifications": [
          {
            "scheme": "CPV"
          }
        ]
      }
    ]
  }
}
```

</td>
      </tr>
      <tr id="BT-26(m)-Lot">
        <td class="field break-all">
            <p><b>BT-26(m)-Lot</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/procedure-lot-part-information.html#classificationSection"></a><br>Classification Type (e.g. CPV)</p><p><i>BT-26:</i> The type of classification describing the purchase (e.g. the CPV).</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='Lot']/cac:ProcurementProject/cac:MainCommodityClassification/cbc:ItemClassificationCode/@listName</span></code>
        </td>
        <td class="mapping">

This field maps to the same object as created for BT-262-Lot.
<a href="operations.md#get-the-item-for-a-procurementprojectlot">Get the item for the ProcurementProjectLot</a> and map to the item's `.classification.scheme`.

```xml
<cac:MainCommodityClassification>
  <cbc:ItemClassificationCode listName="cpv">15311100</cbc:ItemClassificationCode>
</cac:MainCommodityClassification>
```

```json
{
  "tender": {
    "items": [
      {
        "classification": {
          "scheme": "CPV"
        },
        "relatedLots": [
          "LOT-0001"
        ]
      }
    ]
  }
}
```

</td>
      </tr>
      <tr id="BT-26(m)-Part">
        <td class="field break-all">
            <p><b>BT-26(m)-Part</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/procedure-lot-part-information.html#classificationSection"></a><br>Classification Type (e.g. CPV)</p><p><i>BT-26:</i> The type of classification describing the purchase (e.g. the CPV).</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='Part']/cac:ProcurementProject/cac:MainCommodityClassification/cbc:ItemClassificationCode/@listName</span></code>
        </td>
        <td class="mapping">

This field maps to the same object as created for BT-262-Part. If no `Item` object was created for `ancestor::MainCommodityClassification`:

- Add an `Item object to the `tender.items\` array.
- Set the item's `id` incrementally.
  Capitalize and map to the item's `.classification.scheme`.

```xml
<cac:MainCommodityClassification>
  <cbc:ItemClassificationCode listName="cpv">15311100</cbc:ItemClassificationCode>
</cac:MainCommodityClassification>
```

```json
{
  "tender": {
    "items": [
      {
        "classification": {
          "scheme": "CPV"
        }
      }
    ]
  }
}
```

</td>
      </tr>
      <tr id="BT-26(m)-Procedure">
        <td class="field break-all">
            <p><b>BT-26(m)-Procedure</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/procedure-lot-part-information.html#classificationSection"></a><br>Classification Type (e.g. CPV)</p><p><i>BT-26:</i> The type of classification describing the purchase (e.g. the CPV).</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProject/cac:MainCommodityClassification/cbc:ItemClassificationCode/@listName</span></code>
        </td>
        <td class="mapping">

This field maps to the same object as created for BT-262-Procedure. If no `Item` object was created for `ancestor::MainCommodityClassification`:

- Add an `Item object to the `tender.items\` array.
- Set the item's `id` incrementally.
  Capitalize and map to the item's `.classification.scheme`.

```xml
<cac:MainCommodityClassification>
  <cbc:ItemClassificationCode listName="cpv">15311100</cbc:ItemClassificationCode>
</cac:MainCommodityClassification>
```

```json
{
  "tender": {
    "items": [
      {
        "classification": {
          "scheme": "CPV"
        }
      }
    ]
  }
}
```

</td>
      </tr>
      <tr id="BT-262-Lot">
        <td class="field break-all">
            <p><b>BT-262-Lot</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/procedure-lot-part-information.html#classificationSection"></a><br>Main Classification Code</p><p><i>BT-262:</i> The code from the classification that best characterises the purchase.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='Lot']/cac:ProcurementProject/cac:MainCommodityClassification/cbc:ItemClassificationCode</span></code>
        </td>
        <td class="mapping">

This field maps to the same object as created for BT-262-Lot.
<a href="operations.md#get-the-item-for-a-procurementprojectlot">Get the item for the ProcurementProjectLot</a> and map to its `.classification.id`.'

```xml
<cac:MainCommodityClassification>
  <cbc:ItemClassificationCode listName="cpv">15311100</cbc:ItemClassificationCode>
</cac:MainCommodityClassification>
```

```json
{
  "tender": {
    "items": [
      {
        "classification": {
          "id": "15311100"
        }
      }
    ]
  }
}
```

</td>
      </tr>
      <tr id="BT-262-Part">
        <td class="field break-all">
            <p><b>BT-262-Part</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/procedure-lot-part-information.html#classificationSection"></a><br>Main Classification Code</p><p><i>BT-262:</i> The code from the classification that best characterises the purchase.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='Part']/cac:ProcurementProject/cac:MainCommodityClassification/cbc:ItemClassificationCode</span></code>
        </td>
        <td class="mapping">

This field maps to the same object as created for BT-26(m)-Part. If no `Item` object was created for `ancestor::MainCommodityClassification`:

- Add an `Item object to the `tender.items\` array.
- Set the item's `id` incrementally.
  Map to the item's `.classification.id`.

```xml
<cac:MainCommodityClassification>
  <cbc:ItemClassificationCode listName="cpv">15311100</cbc:ItemClassificationCode>
</cac:MainCommodityClassification>
```

```json
{
  "tender": {
    "items": [
      {
        "classification": {
          "id": "15311100"
        }
      }
    ]
  }
}
```

</td>
      </tr>
      <tr id="BT-262-Procedure">
        <td class="field break-all">
            <p><b>BT-262-Procedure</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/procedure-lot-part-information.html#classificationSection"></a><br>Main Classification Code</p><p><i>BT-262:</i> The code from the classification that best characterises the purchase.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProject/cac:MainCommodityClassification/cbc:ItemClassificationCode</span></code>
        </td>
        <td class="mapping">

This field maps to the same object as created for BT-26(m)-Pro. If no `Item` object was created for `ancestor::MainCommodityClassification`:

- Add an `Item object to the `tender.items\` array.
- Set the item's `id` incrementally.
  Map to the item's `.classification.id`.

```xml
<cac:MainCommodityClassification>
  <cbc:ItemClassificationCode listName="cpv">15311100</cbc:ItemClassificationCode>
</cac:MainCommodityClassification>
```

```json
{
  "tender": {
    "items": [
      {
        "classification": {
          "id": "15311100"
        }
      }
    ]
  }
}
```

</td>
      </tr>
      <tr id="BT-263-Lot">
        <td class="field break-all">
            <p><b>BT-263-Lot</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/procedure-lot-part-information.html#classificationSection"></a><br>Additional Classification Code</p><p><i>BT-263:</i> An additional code from the classification that also characterises the purchase.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='Lot']/cac:ProcurementProject/cac:AdditionalCommodityClassification/cbc:ItemClassificationCode</span></code>
        </td>
        <td class="mapping">

This field maps to the same `Classification` objects as created for BT-26(a)-Lot.

<a href="operations.md#get-the-item-for-a-procurementprojectlot">Get the item for the ProcurementProjectLot</a>. For each `cac:AdditionalCommodityClassification/cbc:ItemClassificationCode`, add or update a corresponding `Classification` object in the item's `.additionalClassifications` array and map to the classification's `.id`.

```xml
<cac:AdditionalCommodityClassification>
  <cbc:ItemClassificationCode listName="cpv">15311200</cbc:ItemClassificationCode>
</cac:AdditionalCommodityClassification>
```

```json
{
  "tender": {
    "items": [
      {
        "additionalClassifications": [
          {
            "id": "15311200"
          }
        ]
      }
    ]
  }
}
```

</td>
      </tr>
      <tr id="BT-263-Part">
        <td class="field break-all">
            <p><b>BT-263-Part</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/procedure-lot-part-information.html#classificationSection"></a><br>Additional Classification Code</p><p><i>BT-263:</i> An additional code from the classification that also characterises the purchase.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='Part']/cac:ProcurementProject/cac:AdditionalCommodityClassification/cbc:ItemClassificationCode</span></code>
        </td>
        <td class="mapping">

This field maps to the same objects as created for BT-26(a)-Part. If no `Item` objects were created for `ancestor::AdditionalCommodityClassification`:

- Add an `Item object to the `tender.items\` array.
- Set the item's `id` incrementally.
  For each `cac:AdditionalCommodityClassification/cbc:ItemClassificationCode`, add or update a corresponding `Classification` object in the item's `.additionalClassifications` array and map to the classification's `.id`.

```xml
<cac:AdditionalCommodityClassification>
  <cbc:ItemClassificationCode listName="cpv">15311200</cbc:ItemClassificationCode>
</cac:AdditionalCommodityClassification>
```

```json
{
  "tender": {
    "items": [
      {
        "additionalClassifications": [
          {
            "id": "15311200"
          }
        ]
      }
    ]
  }
}
```

</td>
      </tr>
      <tr id="BT-263-Procedure">
        <td class="field break-all">
            <p><b>BT-263-Procedure</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/procedure-lot-part-information.html#classificationSection"></a><br>Additional Classification Code</p><p><i>BT-263:</i> An additional code from the classification that also characterises the purchase.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProject/cac:AdditionalCommodityClassification/cbc:ItemClassificationCode</span></code>
        </td>
        <td class="mapping">

This field maps to the same objects as created for BT-26(a)-Procedure. If no `Item` objects were created for `ancestor::AdditionalCommodityClassification`:

- Add an `Item object to the `tender.items\` array.
- Set the item's `id` incrementally.
  For each `cac:AdditionalCommodityClassification/cbc:ItemClassificationCode`, add or update a corresponding `Classification` object in the item's `.additionalClassifications` and map to the classification's `.id`.

```xml
<cac:AdditionalCommodityClassification>
  <cbc:ItemClassificationCode listName="cpv">15311200</cbc:ItemClassificationCode>
</cac:AdditionalCommodityClassification>
```

```json
{
  "tender": {
    "items": [
      {
        "additionalClassifications": [
          {
            "id": "15311200"
          }
        ]
      }
    ]
  }
}
```

</td>
      </tr>
      <tr id="BT-27-Lot">
        <td class="field break-all">
            <p><b>BT-27-Lot</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/procedure-lot-part-information.html#estimatedValueSection"></a><br>Estimated Value</p><p><i>BT-27:</i> The estimated value of the procurement procedure or lot, over its whole duration, including options and renewals.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='Lot']/cac:ProcurementProject/cac:RequestedTenderTotal/cbc:EstimatedOverallContractAmount</span></code>
        </td>
        <td class="mapping">

<a href="operations.md#get-the-lot-for-a-procurementprojectlot">Get the lot for the ProcurementProjectLot</a>, map to its `.value.amount` and map `currencyID` to its `value.currency`.

```xml
<cac:RequestedTenderTotal>
  <cbc:EstimatedOverallContractAmount currencyID="EUR">250000</cbc:EstimatedOverallContractAmount>
</cac:RequestedTenderTotal>
```

```json
{
  "tender": {
    "lots": [
      {
        "value": {
          "amount": 250000,
          "currency": "EUR"
        }
      }
    ]
  }
}
```

</td>
      </tr>
      <tr id="BT-27-LotsGroup">
        <td class="field break-all">
            <p><b>BT-27-LotsGroup</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/procedure-lot-part-information.html#estimatedValueSection"></a><br>Estimated Value</p><p><i>BT-27:</i> The estimated value of the procurement procedure or lot, over its whole duration, including options and renewals.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='LotsGroup']/cac:ProcurementProject/cac:RequestedTenderTotal/cbc:EstimatedOverallContractAmount</span></code>
        </td>
        <td class="mapping">

<a href="operations.md#get-the-lot-group-for-a-procurementprojectlot">Get the lot group for the ProcurementProjectLot</a>, map to its `.maximumValue.amount` and map `currencyID` to its `maximumValue.currency`.

```xml
<cac:RequestedTenderTotal>
  <cbc:EstimatedOverallContractAmount currencyID="EUR">250000</cbc:EstimatedOverallContractAmount>
</cac:RequestedTenderTotal>
```

```json
{
  "tender": {
    "lotGroups": [
      {
        "maximumValue": {
          "amount": 250000,
          "currency": "EUR"
        }
      }
    ]
  }
}
```

</td>
      </tr>
      <tr id="BT-27-Part">
        <td class="field break-all">
            <p><b>BT-27-Part</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/procedure-lot-part-information.html#estimatedValueSection"></a><br>Estimated Value</p><p><i>BT-27:</i> The estimated value of the procurement procedure or lot, over its whole duration, including options and renewals.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='Part']/cac:ProcurementProject/cac:RequestedTenderTotal/cbc:EstimatedOverallContractAmount</span></code>
        </td>
        <td class="mapping">

Map to `tender.value.amount` and map `currencyID` to `tender.value.currency`.

```xml
<cac:RequestedTenderTotal>
  <cbc:EstimatedOverallContractAmount currencyID="EUR">250000</cbc:EstimatedOverallContractAmount>
</cac:RequestedTenderTotal>
```

```json
{
  "tender": {
    "value": {
      "amount": 250000,
      "currency": "EUR"
    }
  }
}
```

</td>
      </tr>
      <tr id="BT-27-Procedure">
        <td class="field break-all">
            <p><b>BT-27-Procedure</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/procedure-lot-part-information.html#estimatedValueSection"></a><br>Estimated Value</p><p><i>BT-27:</i> The estimated value of the procurement procedure or lot, over its whole duration, including options and renewals.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProject/cac:RequestedTenderTotal/cbc:EstimatedOverallContractAmount</span></code>
        </td>
        <td class="mapping">

Map to `tender.value.amount` and map `currencyID` to `tender.value.currency`.

```xml
<cac:RequestedTenderTotal>
  <cbc:EstimatedOverallContractAmount currencyID="EUR">250000</cbc:EstimatedOverallContractAmount>
</cac:RequestedTenderTotal>
```

```json
{
  "tender": {
    "value": {
      "amount": 250000,
      "currency": "EUR"
    }
  }
}
```

</td>
      </tr>
      <tr id="BT-271-Lot">
        <td class="field break-all">
            <p><b>BT-271-Lot</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/procedure-lot-part-information.html#estimatedValueSection"></a><br>Framework Maximum Value</p><p><i>BT-271:</i> The maximum value of the framework agreement for the procurement procedure or lot, over its whole duration, including options and renewals. This value covers all contracts to be awarded within the framework agreement.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='Lot']/cac:ProcurementProject/cac:RequestedTenderTotal/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efbc:FrameworkMaximumAmount</span></code>
        </td>
        <td class="mapping">

<a href="operations.md#get-the-lot-for-a-procurementprojectlot">Get the lot for the ProcurementProjectLot</a>, map to its `.techniques.frameworkAgreement.maximumValue.amount` and map `currencyID` to its `techniques.frameworkAgreement.maximumValue.currency`.

```xml
<efext:EformsExtension>
  <efbc:FrameworkMaximumAmount currencyID="EUR">120000</efbc:FrameworkMaximumAmount>
</efext:EformsExtension>
```

```json
{
  "tender": {
    "lots": [
      {
        "techniques": {
          "frameworkAgreement": {
            "maximumValue": {
              "amount": 120000,
              "currency": "EUR"
            }
          }
        }
      }
    ]
  }
}
```

</td>
      </tr>
      <tr id="BT-271-LotsGroup">
        <td class="field break-all">
            <p><b>BT-271-LotsGroup</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/procedure-lot-part-information.html#estimatedValueSection"></a><br>Framework Maximum Value</p><p><i>BT-271:</i> The maximum value of the framework agreement for the procurement procedure or lot, over its whole duration, including options and renewals. This value covers all contracts to be awarded within the framework agreement.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='LotsGroup']/cac:ProcurementProject/cac:RequestedTenderTotal/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efbc:FrameworkMaximumAmount</span></code>
        </td>
        <td class="mapping">

<a href="operations.md#get-the-lot-group-for-a-procurementprojectlot">Get the lot group for the ProcurementProjectLot</a>, map to its `.techniques.frameworkAgreement.maximumValue.amount` and map `currencyID` to its `techniques.frameworkAgreement.maximumValue.currency`.

```xml
<efext:EformsExtension>
  <efbc:FrameworkMaximumAmount currencyID="EUR">120000</efbc:FrameworkMaximumAmount>
</efext:EformsExtension>
```

```json
{
  "tender": {
    "lotGroups": [
      {
        "techniques": {
          "frameworkAgreement": {
            "maximumValue": {
              "amount": 120000,
              "currency": "EUR"
            }
          }
        }
      }
    ]
  }
}
```

</td>
      </tr>
      <tr id="BT-271-Procedure">
        <td class="field break-all">
            <p><b>BT-271-Procedure</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/procedure-lot-part-information.html#estimatedValueSection"></a><br>Framework Maximum Value</p><p><i>BT-271:</i> The maximum value of the framework agreement for the procurement procedure or lot, over its whole duration, including options and renewals. This value covers all contracts to be awarded within the framework agreement.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProject/cac:RequestedTenderTotal/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efbc:FrameworkMaximumAmount</span></code>
        </td>
        <td class="mapping">

Map to `tender.techniques.frameworkAgreement.maximumValue.amount`. Map `@currencyID` to `tender.techniques.frameworkAgreement.maximumValue.currency`.

```xml
<efext:EformsExtension>
  <efbc:FrameworkMaximumAmount currencyID="EUR">120000</efbc:FrameworkMaximumAmount>
</efext:EformsExtension>
```

```json
{
  "tender": {
    "techniques": {
      "frameworkAgreement": {
        "maximumValue": {
          "amount": 120000,
          "currency": "EUR"
        }
      }
    }
  }
}
```

</td>
      </tr>
      <tr id="BT-300-Lot">
        <td class="field break-all">
            <p><b>BT-300-Lot</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/procedure-lot-part-information.html#additionalInfoSection"></a><br>Additional Information</p><p><i>BT-300:</i> Any further information not mentioned in other sections of the notice.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='Lot']/cac:ProcurementProject/cbc:Note</span></code>
        </td>
        <td class="mapping">

<a href="operations.md#get-the-lot-for-a-procurementprojectlot">Get the lot for the ProcurementProjectLot</a> and append to its `.description`.

This results in a loss of structure.

```xml
<cbc:Note languageID="ENG">For the current procedure ...</cbc:Note>
```

```json
{
  "tender": {
    "lots": [
      {
        "description": "For the current procedure ..."
      }
    ]
  }
}
```

</td>
      </tr>
      <tr id="BT-300-LotsGroup">
        <td class="field break-all">
            <p><b>BT-300-LotsGroup</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/procedure-lot-part-information.html#additionalInfoSection"></a><br>Additional Information</p><p><i>BT-300:</i> Any further information not mentioned in other sections of the notice.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='LotsGroup']/cac:ProcurementProject/cbc:Note</span></code>
        </td>
        <td class="mapping">

<a href="operations.md#get-the-lot-group-for-a-procurementprojectlot">Get the lot group for the ProcurementProjectLot</a> and append to its `.description`.

This results in a loss of structure.

```xml
<cbc:Note languageID="ENG">For the current procedure ...</cbc:Note>
```

```json
{
  "tender": {
    "lotGroups": [
      {
        "description": "For the current procedure ..."
      }
    ]
  }
}
```

</td>
      </tr>
      <tr id="BT-300-Part">
        <td class="field break-all">
            <p><b>BT-300-Part</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/procedure-lot-part-information.html#additionalInfoSection"></a><br>Additional Information</p><p><i>BT-300:</i> Any further information not mentioned in other sections of the notice.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='Part']/cac:ProcurementProject/cbc:Note</span></code>
        </td>
        <td class="mapping">

Map to the release's `description`.

```xml
<cbc:Note languageID="ENG">For the current procedure ...</cbc:Note>
```

```json
{
  "description": "For the current procedure..."
}
```

</td>
      </tr>
      <tr id="BT-300-Procedure">
        <td class="field break-all">
            <p><b>BT-300-Procedure</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/procedure-lot-part-information.html#additionalInfoSection"></a><br>Additional Information</p><p><i>BT-300:</i> Any further information not mentioned in other sections of the notice.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProject/cbc:Note</span></code>
        </td>
        <td class="mapping">

Map to the release's `description`

```xml
<cbc:Note languageID="ENG">For the current procedure ...</cbc:Note>
```

```json
{
  "description": "For the current procedure..."
}
```

</td>
      </tr>
      <tr id="BT-31-Procedure">
        <td class="field break-all">
            <p><b>BT-31-Procedure</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/procedure-lot-part-information.html#maxLotsSection"></a><br>Lots Max Allowed</p><p><i>BT-31:</i> The maximum number of lots for which one tenderer can submit tenders.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:TenderingTerms/cac:LotDistribution/cbc:MaximumLotsSubmittedNumeric</span></code>
        </td>
        <td class="mapping">

Map to `tender.lotDetails.maximumLotsBidPerSupplier`

```xml
<cac:LotDistribution>
  <cbc:MaximumLotsSubmittedNumeric>6</cbc:MaximumLotsSubmittedNumeric>
</cac:LotDistribution>
```

```json
{
  "tender": {
    "lotDetails": {
      "maximumLotsBidPerSupplier": 6
    }
  }
}
```

</td>
      </tr>
      <tr id="BT-3201-Tender">
        <td class="field break-all">
            <p><b>BT-3201-Tender</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/competition-results.html#lotTenderSection"></a><br>Tender Identifier</p><p><i>BT-3201:</i> An identifier of a tender. The information in the tender section refers to this tender.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:NoticeResult/efac:LotTender/efac:TenderReference/cbc:ID</span></code>
        </td>
        <td class="mapping">

<a href="operations.md#get-the-bid-for-a-lottender">Get the bid for the LotTender</a>, and map to its `.id`.

```xml
<efac:TenderReference>
  <cbc:ID>BID ABD/GHI-SN/2020-002</cbc:ID>
</efac:TenderReference>
```

```json
{
  "bids": {
    "details": [
      {
        "id": "BID ABD/GHI-SN/2020-002"
      }
    ]
  }
}
```

</td>
      </tr>
      <tr id="BT-3202-Contract">
        <td class="field break-all">
            <p><b>BT-3202-Contract</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/competition-results.html#settledContractSection"></a><br>Contract Tender ID (Reference)</p><p><i>BT-3202:</i> An identifier of the tender or another result that led to this contract.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:NoticeResult/efac:SettledContract/efac:LotTender/cbc:ID</span></code>
        </td>
        <td class="mapping">

- <a href="operations.md#get-the-contract-for-a-settledcontract">Get the contract for the SettledContract</a> and add the value of this field to its `.relatedBids` array.
- Get the `ancestor::efac:NoticeResult/efac:LotTender` whose `/cbc:ID` is equal to the value of this field.
- Get the `ancestor::efac:NoticeResult/efac:TenderingParty` whose `/cbc:ID` matches the `LotTender`'s `/efac:TenderingParty/cbc:ID`.
- For each `ancestor::efac:TenderingParty/efac:Tenderer`, <a href="operations.md#get-the-organization-for-a-tenderer">get the organization for the tenderer</a>, and:
  - Get the `ancestor::efext:EformsExtension/efac:Organizations/efac:Organization/efac:Company` whose `/cac:PartyIdentification/cbc:ID` is equal to the organization's `.id`, and:
    - Add 'supplier' to the organization's `.roles` array.
  - For each `ancestor::efac:NoticeResult/efac:LotResult` with an `/efac:SettledContract/cbc:ID` equal to the value of `ancestor::efac:SettledContract/cbc:ID`:
    - <a href="operations.md#get-the-award-for-a-lotresult">Get the award for the LotResult</a>.
    - Add an `OrganizationReference` to the award's `.suppliers` array, and:
      - Set the organization reference's `.id` to the organization's `.id`.

```xml
<efac:LotTender>
  <cbc:ID schemeName="tender">TEN-0001</cbc:ID>
</efac:LotTender>
```

```json
{
  "parties": [
    {
      "id": "ORG-0001",
      "roles": [
        "supplier"
      ]
    }
  ],
  "awards": [
    {
      "suppliers": [
        {
          "id": "ORG-0001"
        }
      ]
    }
  ],
  "contracts": [
    {
      "relatedBids": [
        "TEN-0001"
      ]
    }
  ]
}
```

</td>
      </tr>
      <tr id="BT-33-Procedure">
        <td class="field break-all">
            <p><b>BT-33-Procedure</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/procedure-lot-part-information.html#maxLotsSection"></a><br>Lots Max Awarded</p><p><i>BT-33:</i> The maximum number of lots for which contract(s) can be awarded to one tenderer.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:TenderingTerms/cac:LotDistribution/cbc:MaximumLotsAwardedNumeric</span></code>
        </td>
        <td class="mapping">

Map to `tender.lotDetails.maximumLotsAwardedPerSupplier`

```xml
<cac:LotDistribution>
  <cbc:MaximumLotsAwardedNumeric>4</cbc:MaximumLotsAwardedNumeric>
</cac:LotDistribution>
```

```json
{
  "tender": {
    "lotDetails": {
      "maximumLotsAwardedPerSupplier": 4
    }
  }
}
```

</td>
      </tr>
      <tr id="BT-330-Procedure">
        <td class="field break-all">
            <p><b>BT-330-Procedure</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/procedure-lot-part-information.html#maxLotsSection"></a><br>Group Identifier</p><p><i>BT-330:</i> The identifier of a group of lots in the procedure.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:TenderingTerms/cac:LotDistribution/cac:LotsGroup/cbc:LotsGroupID</span></code>
        </td>
        <td class="mapping">

If there is a `LotGroup` in `tender.lotGroups` whose `.id` is equal to the value of this field, discard. Otherwise, add a `LotGroup` to `tender.lotGroups` and map to its `.id`.

```xml
<cac:LotsGroup>
  <cbc:LotsGroupID schemeName="LotsGroup">GLO-0001</cbc:LotsGroupID>
</cac:LotsGroup>
```

```json
{
  "tender": {
    "lotGroups": [
      {
        "id": "GLO-0001"
      }
    ]
  }
}
```

</td>
      </tr>
      <tr id="BT-36-Lot">
        <td class="field break-all">
            <p><b>BT-36-Lot</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/procedure-lot-part-information.html#plannedPeriodSection"></a><br>Duration Period</p><p><i>BT-36:</i> The (estimated) period from the start to the end of the contract, framework agreement, dynamic purchasing system or qualification system. This shall include any options and renewals.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='Lot']/cac:ProcurementProject/cac:PlannedPeriod/cbc:DurationMeasure</span></code>
        </td>
        <td class="mapping">

<a href="operations.md#get-the-lot-for-a-procurementprojectlot">Get the lot for the ProcurementProjectLot</a>.

If `@unitCode` is set to "DAY", map to the lot's `.contractPeriod.durationInDays`.

Otherwise, if `@unitCode` is set to "MONTH", multiply by 30, or, if `@unitCode` is set to "YEAR", multiply by 365. In either case, map the result to the lot's `.contractPeriod.durationInDays`.

```xml
<cac:PlannedPeriod>
  <cbc:DurationMeasure unitCode="DAY">3</cbc:DurationMeasure>
</cac:PlannedPeriod>
```

```json
{
  "tender": {
    "lots": [
      {
        "contractPeriod": {
          "durationInDays": 3
        }
      }
    ]
  }
}
```

</td>
      </tr>
      <tr id="BT-36-Part">
        <td class="field break-all">
            <p><b>BT-36-Part</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/procedure-lot-part-information.html#plannedPeriodSection"></a><br>Duration Period</p><p><i>BT-36:</i> The (estimated) period from the start to the end of the contract, framework agreement, dynamic purchasing system or qualification system. This shall include any options and renewals.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='Part']/cac:ProcurementProject/cac:PlannedPeriod/cbc:DurationMeasure</span></code>
        </td>
        <td class="mapping">

If `@unitCode` is set to "DAY", map to `tender.contractPeriod.durationInDays`.

If `@unitCode` is set to "MONTH", multiply by 30. If `@unitCode` is set to "YEAR", multiply by 365. In either case, map the result to `tender.contractPeriod.durationInDays`. If `@unitCode` is set to a specific day of the week or month map equivalent number of days to `tender.contractPeriod.durationInDays`.

```xml
<cac:PlannedPeriod>
  <cbc:DurationMeasure unitCode="DAY">3</cbc:DurationMeasure>
</cac:PlannedPeriod>
```

```json
{
  "tender": {
    "contractPeriod": {
      "durationInDays": 3
    }
  }
}
```

</td>
      </tr>
      <tr id="BT-40-Lot">
        <td class="field break-all">
            <p><b>BT-40-Lot</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/procedure-lot-part-information.html#selectionCriteriaSection"></a><br>Selection Criteria Second Stage Invite</p><p><i>BT-40:</i> The criteria (or criterion) will (only) be used to select the candidates to be invited for the second stage of the procedure (if a maximum number of candidates was set).</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='Lot']/cac:TenderingTerms/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:SelectionCriteria/efbc:SecondStageIndicator</span></code>
        </td>
        <td class="mapping">

If `cbc:CalculationExpressionCode[@listName="usage"]` is not set to "used", discard. Otherwise, this field is maps to the same `SelectionCriterion` objects as created for BT-747, BT-749, BT-750, BT-752, BT-7531 and BT-7532.

- <a href="operations.md#get-the-lot-for-a-procurementprojectlot">Get the lot for the ProcurementProjectLot</a>.
- For each `efac:SelectionCriteria`, add or update a corresponding `SelectionCriterion` object in the lot's `.selectionCriteria.criteria`.
- Set the criterion's `.forReduction` to `true`.

```xml
<efac:SelectionCriteria>
  <efbc:SecondStageIndicator>true</efbc:SecondStageIndicator>
</efac:SelectionCriteria>
```

```json
{
  "tender": {
    "lots": [
      {
        "selectionCriteria": {
          "criteria": [
            {
              "forReduction": true
            }
          ]
        }
      }
    ]
  }
}
```

</td>
      </tr>
      <tr id="BT-41-Lot">
        <td class="field break-all">
            <p><b>BT-41-Lot</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/procedure-lot-part-information.html#awardConsequencesSection"></a><br>Following Contract</p><p><i>BT-41:</i> Any service contract following the contest will be awarded to one of the winners of the contest.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='Lot']/cac:TenderingTerms/cac:AwardingTerms/cbc:FollowupContractIndicator</span></code>
        </td>
        <td class="mapping">

<a href="operations.md#get-the-lot-for-a-procurementprojectlot">Get the lot for the ProcurementProjectLot</a> and and set its `.designContest.followUpContracts` to `true`.

```xml
<cbc:FollowupContractIndicator>true</cbc:FollowupContractIndicator>
```

```json
{
  "tender": {
    "lots": [
      {
        "designContest": {
          "followUpContracts": true
        }
      }
    ]
  }
}
```

</td>
      </tr>
      <tr id="BT-42-Lot">
        <td class="field break-all">
            <p><b>BT-42-Lot</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/procedure-lot-part-information.html#awardConsequencesSection"></a><br>Jury Decision Binding</p><p><i>BT-42:</i> The decision of the jury is binding on the buyer.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='Lot']/cac:TenderingTerms/cac:AwardingTerms/cbc:BindingOnBuyerIndicator</span></code>
        </td>
        <td class="mapping">

<a href="operations.md#get-the-lot-for-a-procurementprojectlot">Get the lot for the ProcurementProjectLot</a> and set its `.designContest.bindingJuryDecision` to `true`.

```xml
<cbc:BindingOnBuyerIndicator>true</cbc:BindingOnBuyerIndicator>
```

```json
{
  "tender": {
    "lots": [
      {
        "designContest": {
          "bindingJuryDecision": true
        }
      }
    ]
  }
}
```

</td>
      </tr>
      <tr id="BT-44-Lot">
        <td class="field break-all">
            <p><b>BT-44-Lot</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/procedure-lot-part-information.html#prizeSection"></a><br>Prize Rank</p><p><i>BT-44:</i> The place (e.g. first place, second place) in a design contest, innovation partnership or competitive dialogue that receives the prize.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='Lot']/cac:TenderingTerms/cac:AwardingTerms/cac:Prize/cbc:RankCode</span></code>
        </td>
        <td class="mapping">

This field maps to the same `Prize` objects as created for BT-45-Lot and BT-644-Lot.

<a href="operations.md#get-the-lot-for-a-procurementprojectlot">Get the lot for the ProcurementProjectLot</a>.

For each `cac:Prize`, add or update the corresponding `Prize` object in the lot's `.designContest.prizes.details` array and set its `.id` incrementally. The position of the prize object in the `.details` array determines the rank of the prize. Example: `.details[0]` should return the highest ranking prize, `.details[1]` the second highest ranking prize, etc.

```xml
<cac:Prize>
  <cbc:RankCode>1</cbc:RankCode>
</cac:Prize>
```

```json
{
  "tender": {
    "lots": [
      {
        "designContest": {
          "prizes": {
            "details": [
              {
                "id": "1"
              }
            ]
          }
        }
      }
    ]
  }
}
```

</td>
      </tr>
      <tr id="BT-45-Lot">
        <td class="field break-all">
            <p><b>BT-45-Lot</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/procedure-lot-part-information.html#prizeSection"></a><br>Rewards Other</p><p><i>BT-45:</i> Further information about follow-up contracts, prizes and payments (for example non-monetary prizes, payments given for participation).</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='Lot']/cac:TenderingTerms/cac:AwardingTerms/cac:Prize/cbc:Description</span></code>
        </td>
        <td class="mapping">

This field maps to the same `Prize` objects as created for BT-44-Lot and BT-644-Lot.

<a href="operations.md#get-the-lot-for-a-procurementprojectlot">Get the lot for the ProcurementProjectLot</a>.
For each `cac:Prize`, add or update the corresponding `Prize` object in the lot's `.designContest.prizes.details` array and map to its `description`.

```xml
<cac:Prize>
  <cbc:Description languageID="ENG">The first prize winner will be awarded ...</cbc:Description>
</cac:Prize>
```

```json
{
  "tender": {
    "lots": [
      {
        "designContest": {
          "prizes": {
            "details": [
              {
                "description": "The first prize winner will be awarded ..."
              }
            ]
          }
        }
      }
    ]
  }
}
```

</td>
      </tr>
      <tr id="BT-46-Lot">
        <td class="field break-all">
            <p><b>BT-46-Lot</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/procedure-lot-part-information.html#jurySection"></a><br>Jury Member Name</p><p><i>BT-46:</i> A name of the jury member.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='Lot']/cac:TenderingTerms/cac:AwardingTerms/cac:TechnicalCommitteePerson/cbc:FamilyName</span></code>
        </td>
        <td class="mapping">

<a href="operations.md#get-the-lot-for-a-procurementprojectlot">Get the lot for the ProcurementProjectLot</a>, add a `JuryMember` object to its `.designContest.juryMembers` array, and map to the jury member's `.name`

```xml
<cac:TechnicalCommitteePerson>
  <cbc:FamilyName>Mrs Pamela Smith</cbc:FamilyName>
</cac:TechnicalCommitteePerson>
```

```json
{
  "tender": {
    "lots": [
      {
        "designContest": {
          "juryMembers": [
            {
              "name": "Mrs Pamela Smith"
            }
          ]
        }
      }
    ]
  }
}
```

</td>
      </tr>
      <tr id="BT-47-Lot">
        <td class="field break-all">
            <p><b>BT-47-Lot</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/procedure-lot-part-information.html#shortlistSection"></a><br>Participant Name</p><p><i>BT-47:</i> A name of an already selected participant. A participant could have been selected already at the time of the publication of the design contest notice because, for example, the information about the participation of a world-renowned architect is intended to promote the contest amongst other potential participants.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='Lot']/cac:TenderingTerms/cac:EconomicOperatorShortList/cac:PreSelectedParty/cac:PartyName/cbc:Name</span></code>
        </td>
        <td class="mapping">

- <a href="operations.md#add-a-party">Add a party</a>, add 'selectedParticipant' to its `.roles`, and map to its `.name`.
- <a href="operations.md#get-the-lot-for-a-procurementprojectlot">Get the lot for the ProcurementProjectLot</a>, add an `OrganizationReference` object to its `.designContest.selectedParticipants` array and set the organization reference's `.id` to the party's `.id`.

```xml
<cac:PartyName>
  <cbc:Name>Mr P. Sanchez</cbc:Name>
</cac:PartyName>
```

```json
{
  "parties": [
    {
      "name": "Mr P. Sanchez",
      "roles": [
        "selectedParticipant"
      ],
      "id": "1"
    }
  ],
  "tender": {
    "lots": [
      {
        "designContest": {
          "selectedParticipants": [
            {
              "id": "1",
              "name": "Mr P. Sanchez"
            }
          ]
        }
      }
    ]
  }
}
```

</td>
      </tr>
      <tr id="BT-50-Lot">
        <td class="field break-all">
            <p><b>BT-50-Lot</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/procedure-lot-part-information.html#maxCandidatesSection"></a><br>Minimum Candidates</p><p><i>BT-50:</i> The minimum number of candidates to be invited for the second stage of the procedure.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='Lot']/cac:TenderingProcess/cac:EconomicOperatorShortList/cbc:MinimumQuantity</span></code>
        </td>
        <td class="mapping">

<a href="operations.md#get-the-lot-for-a-procurementprojectlot">Get the lot for the ProcurementProjectLot</a> and map to its `.secondStage.minimumCandidates`.

```xml
<cac:EconomicOperatorShortList>
  <cbc:MinimumQuantity>3</cbc:MinimumQuantity>
</cac:EconomicOperatorShortList>
```

```json
{
  "tender": {
    "lots": [
      {
        "secondStage": {
          "minimumCandidates": 3
        }
      }
    ]
  }
}
```

</td>
      </tr>
      <tr id="BT-500-Organization-Company">
        <td class="field break-all">
            <p><b>BT-500-Organization-Company</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/parties.html#_general_structure_of_an_organization_related_information"></a><br>Organisation Name</p><p><i>BT-500:</i> The official name of the organisation.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:Organizations/efac:Organization/efac:Company/cac:PartyName/cbc:Name</span></code>
        </td>
        <td class="mapping">

<a href="operations.md#get-the-organization-for-a-company">Get the organization for the company</a> and map to the organization's `.name`.

```xml
<cac:PartyName>
  <cbc:Name languageID="ENG">Ministry of Education</cbc:Name>
</cac:PartyName>
```

```json
{
  "parties": [
    {
      "name": "Ministry of Education"
    }
  ]
}
```

</td>
      </tr>
      <tr id="BT-500-Organization-TouchPoint">
        <td class="field break-all">
            <p><b>BT-500-Organization-TouchPoint</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/parties.html#_general_structure_of_an_organization_related_information"></a><br>Name</p><p><i>BT-500:</i> The official name of the organisation.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:Organizations/efac:Organization/efac:TouchPoint/cac:PartyName/cbc:Name</span></code>
        </td>
        <td class="mapping">

<a href="operations.md#get-the-organization-for-a-touchpoint">Get the organization for the touchpoint</a> and map to the organization's `.name`.

```xml
<cac:PartyName>
  <cbc:Name languageID="ENG">Ministry of Education</cbc:Name>
</cac:PartyName>
```

```json
{
  "parties": [
    {
      "name": "Ministry of Education"
    }
  ]
}
```

</td>
      </tr>
      <tr id="BT-500-UBO">
        <td class="field break-all">
            <p><b>BT-500-UBO</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/parties.html#ultimateBeneficialOwnerSection"></a><br>UBO Name</p><p><i>BT-500:</i> The official name of the organisation.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:Organizations/efac:UltimateBeneficialOwner/cbc:FamilyName</span></code>
        </td>
        <td class="mapping">

<a href="operations.md#get-the-person-for-an-ultimate-beneficial-owner">Get the person for the ultimate beneficial owner</a> and map to the person's `.name`.

```xml
<efac:UltimateBeneficialOwner>
  <cbc:FamilyName>Mouse</cbc:FamilyName>
</efac:UltimateBeneficialOwner>
```

```json
{
  "parties": [
    {
      "beneficialOwners": [
        {
          "name": "Mouse"
        }
      ]
    }
  ]
}
```

</td>
      </tr>
      <tr id="BT-501-Organization-Company">
        <td class="field break-all">
            <p><b>BT-501-Organization-Company</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/parties.html#_general_structure_of_an_organization_related_information"></a><br>Organisation Identifier</p><p><i>BT-501:</i> An identifier of the organisation. All of the organisation's identifiers shall be given.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:Organizations/efac:Organization/efac:Company/cac:PartyLegalEntity/cbc:CompanyID</span></code>
        </td>
        <td class="mapping">

<a href="operations.md#get-the-organization-for-a-company">Get the organization for the company</a>, map to the organization's `.identifier.id` and <a href="https://standard.open-contracting.org/1.1/en/schema/identifiers/#organization-ids">set `.identifier.scheme`</a>.

```xml
<efac:Organization>
  <efac:Company>
    <cac:PartyLegalEntity>
      <cbc:CompanyID>XYZ</cbc:CompanyID>
    </cac:PartyLegalEntity>
  </efac:Company>
</efac:Organization>
```

```json
{
  "parties": [
    {
      "identifier": {
        "id": "XYZ"
      }
    }
  ]
}
```

</td>
      </tr>
      <tr id="BT-5010-Lot">
        <td class="field break-all">
            <p><b>BT-5010-Lot</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/procedure-lot-part-information.html#EUFundsSection"></a><br>EU Funds Financing Identifier</p><p><i>BT-5010:</i> An identifier of the Union programme used to at least partially finance the contract. The most concrete information must be given (e.g. grant agreement number, national identifier, project acronym, contract number).</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='Lot']/cac:TenderingTerms/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:Funding/efbc:FinancingIdentifier</span></code>
        </td>
        <td class="mapping">

- Get the `Organization` object whose `.name` is 'European Union' and add 'funder' to its `.roles`.
- If none exists yet:
  - <a href="operations.md#add-a-party">Add a party</a>.
  - Set its `.name` to 'European Union'.
  - Add 'funder' to its `.roles`.
- This field maps to the same `finance` objects as created for BT-6140-Lot and BT-7220-Lot.
- <a href="operations.md#get-the-lot-for-a-procurementprojectlot">Get the lot for the ProcurementProjectLot</a>.
- For each `efac:Funding`, add or update the corresponding `Finance` object in the budget's `.finance` array and map to its `.id`.
  - Add the lot's identifier to `.relatedLots`.
  - Set its `.financingParty.name` to 'European Union'.
  - Set its `.financingParty.id` to the party's `.id`.

```xml
<efac:Funding>
  <efbc:FinancingIdentifier>CON_PRO-123/ABC</efbc:FinancingIdentifier>
</efac:Funding>
```

```json
{
  "parties": [
    {
      "id": "1",
      "name": "European Union",
      "roles": [
        "funder"
      ]
    }
  ],
  "planning": {
    "budget": {
      "finance": [
        {
          "id": "CON_PRO-123/ABC",
          "financingParty": {
            "id": "1",
            "name": "European Union"
          }
        }
      ]
    }
  }
}
```

</td>
      </tr>
      <tr id="BT-5011-Contract">
        <td class="field break-all">
            <p><b>BT-5011-Contract</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/competition-results.html#settledContractSection"></a><br>Contract EU Funds Financing Identifier</p><p><i>BT-5011:</i> An identifier of the Union programme used to at least partially finance the contract. The most concrete information must be given (e.g. grant agreement number, national identifier, project acronym, contract number) </p>
            <code class="docutils literal notranslate"><span class="pre">/*/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:NoticeResult/efac:SettledContract/efac:Funding/efbc:FinancingIdentifier</span></code>
        </td>
        <td class="mapping">

- Get the `Organization` object whose `.name` is 'European Union' and add 'funder' to its `.roles`.
- If none exists yet:
  - <a href="operations.md#add-a-party">Add a party</a>.
  - Set its `.name` to 'European Union'.
  - Add 'funder' to its `.roles`.
- This field maps to the same `finance` objects as created for BT-6110-Contract and BT-722-Contract.
- <a href="operations.md#get-the-contract-for-a-settledcontract">Get the contract for the SettledContract</a>.
- For each `efac:Funding`, add or update the corresponding `Finance` object in the contract's `.finance` array and map to its `.id`.
  - Set its `.financingParty.name` to 'European Union'.
  - Set its `.financingParty.id` to the party's `.id`.

```xml
<efac:Funding>
  <efbc:FinancingIdentifier>2021/1234</efbc:FinancingIdentifier>
</efac:Funding>
```

```json
{
  "parties": [
    {
      "id": "1",
      "name": "European Union",
      "roles": [
        "funder"
      ]
    }
  ],
  "contracts": [
    {
      "finance": [
        {
          "id": "2021/1234",
          "financingParty": {
            "id": "1",
            "name": "European Union"
          }
        }
      ]
    }
  ]
}
```

</td>
      </tr>
      <tr id="BT-502-Organization-Company">
        <td class="field break-all">
            <p><b>BT-502-Organization-Company</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/parties.html#_general_structure_of_an_organization_related_information"></a><br>Organisation Contact Point</p><p><i>BT-502:</i> The name of the department or other contact point for communicating with the organisation. To avoid unnecessary processing of personal data, the contact point shall allow the identification of a physical person only when necessary (in the sense of European Parliament and Council Regulation (EU) 2016/679 and European Parliament and Council Regulation (EU) 2018/1725).</p>
            <code class="docutils literal notranslate"><span class="pre">/*/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:Organizations/efac:Organization/efac:Company/cac:Contact/cbc:Name</span></code>
        </td>
        <td class="mapping">

<a href="operations.md#get-the-organization-for-a-company">Get the organization for the company</a> and map to the organization's `.contactPoint.name`

```xml
<cac:Contact>
  <cbc:Name>Press Department</cbc:Name>
</cac:Contact>
```

```json
{
  "parties": [
    {
      "contactPoint": {
        "name": "Press Department"
      }
    }
  ]
}
```

</td>
      </tr>
      <tr id="BT-502-Organization-TouchPoint">
        <td class="field break-all">
            <p><b>BT-502-Organization-TouchPoint</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/parties.html#_general_structure_of_an_organization_related_information"></a><br>Contact Point</p><p><i>BT-502:</i> The name of the department or other contact point for communicating with the organisation. To avoid unnecessary processing of personal data, the contact point shall allow the identification of a physical person only when necessary (in the sense of European Parliament and Council Regulation (EU) 2016/679 and European Parliament and Council Regulation (EU) 2018/1725).</p>
            <code class="docutils literal notranslate"><span class="pre">/*/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:Organizations/efac:Organization/efac:TouchPoint/cac:Contact/cbc:Name</span></code>
        </td>
        <td class="mapping">

<a href="operations.md#get-the-organization-for-a-touchpoint">Get the organization for the touchpoint</a> and map to the organization's `.contactPoint.name`.

```xml
<cac:Contact>
  <cbc:Name>Head of Legal Department</cbc:Name>
</cac:Contact>
```

```json
{
  "parties": [
    {
      "contactPoint": {
        "name": "Head of Legal Department"
      }
    }
  ]
}
```

</td>
      </tr>
      <tr id="BT-503-Organization-Company">
        <td class="field break-all">
            <p><b>BT-503-Organization-Company</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/parties.html#_general_structure_of_an_organization_related_information"></a><br>Organisation Contact Telephone Number</p><p><i>BT-503:</i> The telephone number for contacting the organisation. To avoid unnecessary processing of personal data, the telephone number shall allow the identification of a physical person only when necessary (in the sense of the Regulation (EU) 2016/679 and Regulation (EU) 2018/1725).</p>
            <code class="docutils literal notranslate"><span class="pre">/*/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:Organizations/efac:Organization/efac:Company/cac:Contact/cbc:Telephone</span></code>
        </td>
        <td class="mapping">

<a href="operations.md#get-the-organization-for-a-company">Get the organization for the company</a> and map to the organization's `.contactPoint.telephone`

```xml
<cac:Contact>
  <cbc:Telephone>+123 45678</cbc:Telephone>
</cac:Contact>
```

```json
{
  "parties": [
    {
      "contactPoint": {
        "telephone": "+123 45678"
      }
    }
  ]
}
```

</td>
      </tr>
      <tr id="BT-503-Organization-TouchPoint">
        <td class="field break-all">
            <p><b>BT-503-Organization-TouchPoint</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/parties.html#_general_structure_of_an_organization_related_information"></a><br>Contact Telephone Number</p><p><i>BT-503:</i> The telephone number for contacting the organisation. To avoid unnecessary processing of personal data, the telephone number shall allow the identification of a physical person only when necessary (in the sense of the Regulation (EU) 2016/679 and Regulation (EU) 2018/1725).</p>
            <code class="docutils literal notranslate"><span class="pre">/*/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:Organizations/efac:Organization/efac:TouchPoint/cac:Contact/cbc:Telephone</span></code>
        </td>
        <td class="mapping">

<a href="operations.md#get-the-organization-for-a-touchpoint">Get the organization for the touchpoint</a> and map to the organization's `.contactPoint.telephone`

```xml
<cac:Contact>
  <cbc:Telephone>+123 45678</cbc:Telephone>
</cac:Contact>
```

```json
{
  "parties": [
    {
      "contactPoint": {
        "telephone": "+123 45678"
      }
    }
  ]
}
```

</td>
      </tr>
      <tr id="BT-503-UBO">
        <td class="field break-all">
            <p><b>BT-503-UBO</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/parties.html#ultimateBeneficialOwnerSection"></a><br>UBO Telephone Number</p><p><i>BT-503:</i> The telephone number for contacting the organisation. To avoid unnecessary processing of personal data, the telephone number shall allow the identification of a physical person only when necessary (in the sense of the Regulation (EU) 2016/679 and Regulation (EU) 2018/1725).</p>
            <code class="docutils literal notranslate"><span class="pre">/*/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:Organizations/efac:UltimateBeneficialOwner/cac:Contact/cbc:Telephone</span></code>
        </td>
        <td class="mapping">

<a href="operations.md#get-the-person-for-an-ultimate-beneficial-owner">Get the person for the ultimate beneficial owner</a> and map to the person's `.telephone`.

```xml
<efac:UltimateBeneficialOwner>
  <cac:Contact>
    <cbc:Telephone>+123 4567890</cbc:Telephone>
  </cac:Contact>
</efac:UltimateBeneficialOwner>
```

```json
{
  "parties": [
    {
      "beneficialOwners": [
        {
          "telephone": "+123 456789"
        }
      ]
    }
  ]
}
```

</td>
      </tr>
      <tr id="BT-505-Organization-Company">
        <td class="field break-all">
            <p><b>BT-505-Organization-Company</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/parties.html#_general_structure_of_an_organization_related_information"></a><br>Organisation Internet Address</p><p><i>BT-505:</i> The website of the organisation.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:Organizations/efac:Organization/efac:Company/cbc:WebsiteURI</span></code>
        </td>
        <td class="mapping">

<a href="operations.md#get-the-organization-for-a-company">Get the organization for the company</a> and map to the organization's `.details.url`.

```xml
<efac:Company>
  <cbc:WebsiteURI>http://xyz.europa.eu/</cbc:WebsiteURI>
</efac:Company>
```

```json
{
  "parties": [
    {
      "details": {
        "url": "http://xyz.europa.eu/"
      }
    }
  ]
}
```

</td>
      </tr>
      <tr id="BT-505-Organization-TouchPoint">
        <td class="field break-all">
            <p><b>BT-505-Organization-TouchPoint</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/parties.html#_general_structure_of_an_organization_related_information"></a><br>Internet Address</p><p><i>BT-505:</i> The website of the organisation.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:Organizations/efac:Organization/efac:TouchPoint/cbc:WebsiteURI</span></code>
        </td>
        <td class="mapping">

<a href="operations.md#get-the-organization-for-a-touchpoint">Get the organization for the touchpoint</a> and map to the organization's `.details.url`.

```xml
<efac:TouchPoint>
  <cbc:WebsiteURI>http://abc.europa.eu/</cbc:WebsiteURI>
</efac:TouchPoint>
```

```json
{
  "parties": [
    {
      "details": {
        "url": "http://abc.europa.eu/"
      }
    }
  ]
}
```

</td>
      </tr>
      <tr id="BT-506-Organization-Company">
        <td class="field break-all">
            <p><b>BT-506-Organization-Company</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/parties.html#_general_structure_of_an_organization_related_information"></a><br>Organisation Contact Email Address</p><p><i>BT-506:</i> The email address for contacting the organisation. To avoid unnecessary processing of personal data, the email address shall allow the identification of a physical person only when necessary (in the sense of the Regulation (EU) 2016/679 and Regulation (EU) 2018/1725).</p>
            <code class="docutils literal notranslate"><span class="pre">/*/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:Organizations/efac:Organization/efac:Company/cac:Contact/cbc:ElectronicMail</span></code>
        </td>
        <td class="mapping">

<a href="operations.md#get-the-organization-for-a-company">Get the organization for the company</a> and map to the organization's `.contactPoint.email`

```xml
<efac:Organization>
  <efac:Company>
    <cac:Contact>
      <cbc:ElectronicMail>press@xyz.europa.eu</cbc:ElectronicMail>
    </cac:Contact>
  </efac:Company>
</efac:Organization>
```

```json
{
  "parties": [
    {
      "contactPoint": {
        "email": "press@xyz.europa.eu"
      }
    }
  ]
}
```

</td>
      </tr>
      <tr id="BT-506-Organization-TouchPoint">
        <td class="field break-all">
            <p><b>BT-506-Organization-TouchPoint</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/parties.html#_general_structure_of_an_organization_related_information"></a><br>Contact Email Address</p><p><i>BT-506:</i> The email address for contacting the organisation. To avoid unnecessary processing of personal data, the email address shall allow the identification of a physical person only when necessary (in the sense of the Regulation (EU) 2016/679 and Regulation (EU) 2018/1725).</p>
            <code class="docutils literal notranslate"><span class="pre">/*/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:Organizations/efac:Organization/efac:TouchPoint/cac:Contact/cbc:ElectronicMail</span></code>
        </td>
        <td class="mapping">

<a href="operations.md#get-the-organization-for-a-touchpoint">Get the organization for the touchpoint</a> and map to the organization's `.contactPoint.email`

```xml
<efac:Organization>
  <efac:TouchPoint>
    <cac:Contact>
      <cbc:ElectronicMail>abc@xyz.europa.eu</cbc:ElectronicMail>
    </cac:Contact>
  </efac:TouchPoint>a</efac:Organization>
```

```json
{
  "parties": [
    {
      "contactPoint": {
        "email": "press@xyz.europa.eu"
      }
    }
  ]
}
```

</td>
      </tr>
      <tr id="BT-506-UBO">
        <td class="field break-all">
            <p><b>BT-506-UBO</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/parties.html#ultimateBeneficialOwnerSection"></a><br>UBO Email Address</p><p><i>BT-506:</i> The email address for contacting the organisation. To avoid unnecessary processing of personal data, the email address shall allow the identification of a physical person only when necessary (in the sense of the Regulation (EU) 2016/679 and Regulation (EU) 2018/1725).</p>
            <code class="docutils literal notranslate"><span class="pre">/*/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:Organizations/efac:UltimateBeneficialOwner/cac:Contact/cbc:ElectronicMail</span></code>
        </td>
        <td class="mapping">

<a href="operations.md#get-the-person-for-an-ultimate-beneficial-owner">Get the person for the ultimate beneficial owner</a> and map to the person's `.email`.

```xml
<efac:UltimateBeneficialOwner>
  <cac:Contact>
    <cbc:ElectronicMail>mickey.mouse@cheese-universe.com</cbc:ElectronicMail>
  </cac:Contact>
</efac:UltimateBeneficialOwner>
```

```json
{
  "parties": [
    {
      "beneficialOwners": [
        {
          "email": "mickey.mouse@cheese-universe.com"
        }
      ]
    }
  ]
}
```

</td>
      </tr>
      <tr id="BT-507-Organization-Company">
        <td class="field break-all">
            <p><b>BT-507-Organization-Company</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/parties.html#_general_structure_of_an_organization_related_information"></a><br>Organisation Country Subdivision</p><p><i>BT-507:</i> The location according to the common classification of territorial units for statistics (NUTS) of the organisation's physical address. The NUTS3 classification code shall be used.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:Organizations/efac:Organization/efac:Company/cac:PostalAddress/cbc:CountrySubentityCode</span></code>
        </td>
        <td class="mapping">

<a href="operations.md#get-the-organization-for-a-company">Get the organization for the company</a> and map to the organization's `.address.region`.

```xml
<efac:Organization>
  <efac:Company>
    <cac:PostalAddress>
      <cbc:CountrySubentityCode listName="nuts-lvl3">XY374</cbc:CountrySubentityCode>
    </cac:PostalAddress>
  </efac:Company>
</efac:Organization>
```

```json
{
  "parties": [
    {
      "address": {
        "region": "XY374"
      }
    }
  ]
}
```

</td>
      </tr>
      <tr id="BT-507-Organization-TouchPoint">
        <td class="field break-all">
            <p><b>BT-507-Organization-TouchPoint</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/parties.html#_general_structure_of_an_organization_related_information"></a><br>Country Subdivision</p><p><i>BT-507:</i> The location according to the common classification of territorial units for statistics (NUTS) of the organisation's physical address. The NUTS3 classification code shall be used.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:Organizations/efac:Organization/efac:TouchPoint/cac:PostalAddress/cbc:CountrySubentityCode</span></code>
        </td>
        <td class="mapping">

<a href="operations.md#get-the-organization-for-a-touchpoint">Get the organization for the touchpoint</a> and map to the organization's `.address.region`.

```xml
<efac:Organization>
  <efac:TouchPoint>
    <cac:PostalAddress>
      <cbc:CountrySubentityCode listName="nuts-lvl3">XY374</cbc:CountrySubentityCode>
    </cac:PostalAddress>
  </efac:TouchPoint>
</efac:Organization>
```

```json
{
  "parties": [
    {
      "address": {
        "region": "XY374"
      }
    }
  ]
}
```

</td>
      </tr>
      <tr id="BT-507-UBO">
        <td class="field break-all">
            <p><b>BT-507-UBO</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/parties.html#ultimateBeneficialOwnerSection"></a><br>Country Subdivision</p><p><i>BT-507:</i> The location according to the common classification of territorial units for statistics (NUTS) of the organisation's physical address. The NUTS3 classification code shall be used.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:Organizations/efac:UltimateBeneficialOwner/cac:ResidenceAddress/cbc:CountrySubentityCode</span></code>
        </td>
        <td class="mapping">

<a href="operations.md#get-the-person-for-an-ultimate-beneficial-owner">Get the person for the ultimate beneficial owner</a> and map to the person's `.address.region`.

```xml
<efac:UltimateBeneficialOwner>
  <cac:ResidenceAddress>
    <cbc:CountrySubentityCode listName="nuts-lvl3">GBK62</cbc:CountrySubentityCode>
  </cac:ResidenceAddress>
</efac:UltimateBeneficialOwner>
```

```json
{
  "parties": [
    {
      "beneficialOwners": [
        {
          "address": {
            "region": "GBK62"
          }
        }
      ]
    }
  ]
}
```

</td>
      </tr>
      <tr id="BT-5071-Lot">
        <td class="field break-all">
            <p><b>BT-5071-Lot</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/procedure-lot-part-information.html#performancePlaceSection"></a><br>Place Performance Country Subdivision</p><p><i>BT-5071:</i> The location according to the common classification of territorial units for statistics (NUTS). The NUTS3 classification code shall be used.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='Lot']/cac:ProcurementProject/cac:RealizedLocation/cac:Address/cbc:CountrySubentityCode</span></code>
        </td>
        <td class="mapping">

This field maps to the same `Address` objects as created for BT-728-Lot, BT-5131-Lot, BT-5121-Lot, BT-727-Lot, BT-5101-Lot and BT-5141-Lot.

<a href="operations.md#get-the-item-for-a-procurementprojectlot">Get the item for the ProcurementProjectLot</a>.
For each `cac:RealizedLocation`, add or update the corresponding `Address` object in the item's `.deliveryAddresses` array and map to its `.region`.

```xml
<cac:RealizedLocation>
  <cac:Address>
    <cbc:CountrySubentityCode listName="nuts=lvl3">UKG23</cbc:CountrySubentityCode>
  </cac:Address>
</cac:RealizedLocation>
```

```json
{
  "tender": {
    "items": [
      {
        "deliveryAddresses": [
          {
            "region": "UKG23"
          }
        ]
      }
    ]
  }
}
```

</td>
      </tr>
      <tr id="BT-5071-Part">
        <td class="field break-all">
            <p><b>BT-5071-Part</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/procedure-lot-part-information.html#performancePlaceSection"></a><br>Place Performance Country Subdivision</p><p><i>BT-5071:</i> The location according to the common classification of territorial units for statistics (NUTS). The NUTS3 classification code shall be used.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='Part']/cac:ProcurementProject/cac:RealizedLocation/cac:Address/cbc:CountrySubentityCode</span></code>
        </td>
        <td class="mapping">

This field maps to the same `Address` objects as created for BT-728-Part, BT-5131-Part, BT-5121-Part, BT-727-Part, BT-5101-Part and BT-5141-Part.
For each `cac:RealizedLocation`, add or update the corresponding `Address` object in the `tender.deliveryAddresses` array and map to its `.region`.

```xml
<cac:RealizedLocation>
  <cac:Address>
    <cbc:CountrySubentityCode listName="-lvl3">UKG23</cbc:CountrySubentityCode>
  </cac:Address>
</cac:RealizedLocation>
```

```json
{
  "tender": {
    "deliveryAddresses": [
      {
        "region": "UKG23"
      }
    ]
  }
}
```

</td>
      </tr>
      <tr id="BT-5071-Procedure">
        <td class="field break-all">
            <p><b>BT-5071-Procedure</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/procedure-lot-part-information.html#performancePlaceSection"></a><br>Place Performance Country Subdivision</p><p><i>BT-5071:</i> The location according to the common classification of territorial units for statistics (NUTS). The NUTS3 classification code shall be used.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProject/cac:RealizedLocation/cac:Address/cbc:CountrySubentityCode</span></code>
        </td>
        <td class="mapping">

This field maps to the same `Address` objects as created for BT-728-Procedure, BT-5131-Procedure, BT-5121-Procedure, BT-727-Procedure, BT-5101-Procedure and BT-5141-Procedure.
For each `cac:RealizedLocation`, add or update the corresponding `Address` object in the `tender.deliveryAddresses` array and map to its `.region`.

```xml
<cac:RealizedLocation>
  <cac:Address>
    <cbc:CountrySubentityCode listName="nuts-lvl3">UKG23</cbc:CountrySubentityCode>
  </cac:Address>
</cac:RealizedLocation>
```

```json
{
  "tender": {
    "deliveryAddresses": [
      {
        "region": "UKG23"
      }
    ]
  }
}
```

</td>
      </tr>
      <tr id="BT-508-Procedure-Buyer">
        <td class="field break-all">
            <p><b>BT-508-Procedure-Buyer</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/parties.html#_buyer_information"></a><br>Buyer Profile URL</p><p><i>BT-508:</i> The website where the buyer publishes information regarding procurement procedures (e.g. notices, procurement documents).</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ContractingParty/cbc:BuyerProfileURI</span></code>
        </td>
        <td class="mapping">

<a href="operations.md#get-the-organization-for-the-buyer">Get the organization for the buyer</a>. Map to the organization's `.details.buyerProfile`.

```xml
<cac:ContractingParty>
  <cbc:BuyerProfileURI>https://admin-abc.com/public-procurements/</cbc:BuyerProfileURI>
</cac:ContractingParty>
```

```json
{
  "parties": [
    {
      "details": {
        "buyerProfile": "https://admin-abc.com/public-procurements/"
      }
    }
  ]
}
```

</td>
      </tr>
      <tr id="BT-509-Organization-Company">
        <td class="field break-all">
            <p><b>BT-509-Organization-Company</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/parties.html#_general_structure_of_an_organization_related_information"></a><br>Organisation eDelivery Gateway</p><p><i>BT-509:</i> The organisation's uniform resource locator for exchange of data and documents.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:Organizations/efac:Organization/efac:Company/cbc:EndpointID</span></code>
        </td>
        <td class="mapping">

<a href="operations.md#get-the-organization-for-a-company">Get the organization for the company</a> and map to the organization's `.eDeliveryGateway`.

```xml
<efac:Organization>
  <efac:Company>
    <cbc:EndpointID>https://drive.xpertpro.eu/</cbc:EndpointID>
  </efac:Company>
</efac:Organization>
```

```json
{
  "parties": [
    {
      "eDeliveryGateway": "https://drive.xpertpro.eu"
    }
  ]
}
```

</td>
      </tr>
      <tr id="BT-509-Organization-TouchPoint">
        <td class="field break-all">
            <p><b>BT-509-Organization-TouchPoint</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/parties.html#_general_structure_of_an_organization_related_information"></a><br>eDelivery Gateway</p><p><i>BT-509:</i> The organisation's uniform resource locator for exchange of data and documents.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:Organizations/efac:Organization/efac:TouchPoint/cbc:EndpointID</span></code>
        </td>
        <td class="mapping">

<a href="operations.md#get-the-organization-for-a-touchpoint">Get the organization for the touchpoint</a> and map to the organization's `.eDeliveryGateway`.

```xml
<efac:Organization>
  <efac:TouchPoint>
    <cbc:EndpointID>https://drive.xpertpro.eu/</cbc:EndpointID>
  </efac:TouchPoint>
</efac:Organization>
```

```json
{
  "parties": [
    {
      "eDeliveryGateway": "https://drive.xpertpro.eu"
    }
  ]
}
```

</td>
      </tr>
      <tr id="BT-51-Lot">
        <td class="field break-all">
            <p><b>BT-51-Lot</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/procedure-lot-part-information.html#maxCandidatesSection"></a><br>Maximum Candidates Number</p><p><i>BT-51:</i> The maximum number of candidates to be invited for the second stage of the procedure.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='Lot']/cac:TenderingProcess/cac:EconomicOperatorShortList/cbc:MaximumQuantity</span></code>
        </td>
        <td class="mapping">

<a href="operations.md#get-the-lot-for-a-procurementprojectlot">Get the lot for the ProcurementProjectLot</a> and map to its `.secondStage.maximumCandidates`.

```xml
<cac:EconomicOperatorShortList>
  <cbc:MaximumQuantity>10</cbc:MaximumQuantity>
</cac:EconomicOperatorShortList>
```

```json
{
  "tender": {
    "lots": [
      {
        "secondStage": {
          "maximumCandidates": 10
        }
      }
    ]
  }
}
```

</td>
      </tr>
      <tr id="BT-510(a)-Organization-Company">
        <td class="field break-all">
            <p><b>BT-510(a)-Organization-Company</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/parties.html#_general_structure_of_an_organization_related_information"></a><br>Street</p><p><i>BT-510:</i> The name of the street, road, avenue, etc., of the organisation's physical address and further identification (e.g. building number).</p>
            <code class="docutils literal notranslate"><span class="pre">/*/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:Organizations/efac:Organization/efac:Company/cac:PostalAddress/cbc:StreetName</span></code>
        </td>
        <td class="mapping">

<a href="operations.md#get-the-organization-for-a-company">Get the organization for the company</a>, combine the values of `cbc:StreetName`, `cbc:AdditionalStreetName` and each `cac:AddressLine/cbc:Line` in that order, separating each string with ', ' (comma and space) and map to the organization's `address.streetAddress`.

```xml
<efac:Organization>
  <efac:Company>
    <cac:PostalAddress>
      <cbc:StreetName>2, rue de Europe</cbc:StreetName>
    </cac:PostalAddress>
  </efac:Company>
</efac:Organization>
```

```json
{
  "parties": [
    {
      "address": {
        "streetAddress": "2, rue de Europe, Building A, 3rd Floor"
      }
    }
  ]
}
```

</td>
      </tr>
      <tr id="BT-510(a)-Organization-TouchPoint">
        <td class="field break-all">
            <p><b>BT-510(a)-Organization-TouchPoint</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/parties.html#_general_structure_of_an_organization_related_information"></a><br>Street</p><p><i>BT-510:</i> The name of the street, road, avenue, etc., of the organisation's physical address and further identification (e.g. building number).</p>
            <code class="docutils literal notranslate"><span class="pre">/*/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:Organizations/efac:Organization/efac:TouchPoint/cac:PostalAddress/cbc:StreetName</span></code>
        </td>
        <td class="mapping">

<a href="operations.md#get-the-organization-for-a-touchpoint">Get the organization for the touchpoint</a>, combine the values of `cbc:StreetName`, `cbc:AdditionalStreetName` and each `cac:AddressLine/cbc:Line` in that order, separating each string with ', ' (comma and space) and map to the organization's `address.streetAddress`.

```xml
<efac:Organization>
  <efac:TouchPoint>
    <cac:PostalAddress>
      <cbc:StreetName>2, rue de Europe</cbc:StreetName>
    </cac:PostalAddress>
  </efac:TouchPoint>
</efac:Organization>
```

```json
{
  "parties": [
    {
      "address": {
        "streetAddress": "2, rue de Europe, Building A, 3rd Floor"
      }
    }
  ]
}
```

</td>
      </tr>
      <tr id="BT-510(a)-UBO">
        <td class="field break-all">
            <p><b>BT-510(a)-UBO</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/parties.html#ultimateBeneficialOwnerSection"></a><br>Street</p><p><i>BT-510:</i> The name of the street, road, avenue, etc., of the organisation's physical address and further identification (e.g. building number).</p>
            <code class="docutils literal notranslate"><span class="pre">/*/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:Organizations/efac:UltimateBeneficialOwner/cac:ResidenceAddress/cbc:StreetName</span></code>
        </td>
        <td class="mapping">

<a href="operations.md#get-the-person-for-an-ultimate-beneficial-owner">Get the person for the ultimate beneficial owner</a>, combine the values of `cbc:StreetName`, `cbc:AdditionalStreetName` and each `cac:AddressLine/cbc:Line` in that order, separating each string with ', ' (comma and space) and map to the person's `address.streetAddress`.

```xml
<efac:UltimateBeneficialOwner>
  <cac:ResidenceAddress>
    <cbc:StreetName>2 CheeseStreet</cbc:StreetName>
  </cac:ResidenceAddress>
</efac:UltimateBeneficialOwner>
```

```json
{
  "parties": [
    {
      "beneficialOwners": [
        {
          "address": {
            "streetAddress": "2 CheeseStreet, Nelson Building, 2nd floor"
          }
        }
      ]
    }
  ]
}
```

</td>
      </tr>
      <tr id="BT-510(b)-Organization-Company">
        <td class="field break-all">
            <p><b>BT-510(b)-Organization-Company</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/parties.html#_general_structure_of_an_organization_related_information"></a><br>Streetline 1</p><p><i>BT-510:</i> The name of the street, road, avenue, etc., of the organisation's physical address and further identification (e.g. building number).</p>
            <code class="docutils literal notranslate"><span class="pre">/*/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:Organizations/efac:Organization/efac:Company/cac:PostalAddress/cbc:AdditionalStreetName</span></code>
        </td>
        <td class="mapping">

<a href="operations.md#get-the-organization-for-a-company">Get the organization for the company</a>, combine the values of `cbc:StreetName`, `cbc:AdditionalStreetName` and each `cac:AddressLine/cbc:Line` in that order, separating each string with ', ' (comma and space) and map to the organization's `address.streetAddress`.

```xml
<efac:Organization>
  <efac:Company>
    <cac:PostalAddress>
      <cbc:AdditionalStreetName>Building A</cbc:AdditionalStreetName>
    </cac:PostalAddress>
  </efac:Company>
</efac:Organization>
```

```json
{
  "parties": [
    {
      "address": {
        "streetAddress": "2, rue de Europe, Building A, 3rd Floor"
      }
    }
  ]
}
```

</td>
      </tr>
      <tr id="BT-510(b)-Organization-TouchPoint">
        <td class="field break-all">
            <p><b>BT-510(b)-Organization-TouchPoint</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/parties.html#_general_structure_of_an_organization_related_information"></a><br>Streetline 1</p><p><i>BT-510:</i> The name of the street, road, avenue, etc., of the organisation's physical address and further identification (e.g. building number).</p>
            <code class="docutils literal notranslate"><span class="pre">/*/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:Organizations/efac:Organization/efac:TouchPoint/cac:PostalAddress/cbc:AdditionalStreetName</span></code>
        </td>
        <td class="mapping">

<a href="operations.md#get-the-organization-for-a-touchpoint">Get the organization for the touchpoint</a>, combine the values of `cbc:StreetName`, `cbc:AdditionalStreetName` and each `cac:AddressLine/cbc:Line` in that order, separating each string with ', ' (comma and space) and map to the organization's `address.streetAddress`.

```xml
<efac:Organization>
  <efac:TouchPoint>
    <cac:PostalAddress>
      <cbc:AdditionalStreetName>Building A</cbc:AdditionalStreetName>
    </cac:PostalAddress>
  </efac:TouchPoint>
</efac:Organization>
```

```json
{
  "parties": [
    {
      "address": {
        "streetAddress": "2, rue de Europe, Building A, 3rd Floor"
      }
    }
  ]
}
```

</td>
      </tr>
      <tr id="BT-510(b)-UBO">
        <td class="field break-all">
            <p><b>BT-510(b)-UBO</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/parties.html#ultimateBeneficialOwnerSection"></a><br>Streetline 1</p><p><i>BT-510:</i> The name of the street, road, avenue, etc., of the organisation's physical address and further identification (e.g. building number).</p>
            <code class="docutils literal notranslate"><span class="pre">/*/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:Organizations/efac:UltimateBeneficialOwner/cac:ResidenceAddress/cbc:AdditionalStreetName</span></code>
        </td>
        <td class="mapping">

<a href="operations.md#get-the-person-for-an-ultimate-beneficial-owner">Get the person for the ultimate beneficial owner</a>, combine the values of `cbc:StreetName`, `cbc:AdditionalStreetName` and each `cac:AddressLine/cbc:Line` in that order, separating each string with ', ' (comma and space) and map to the person's `address.streetAddress`.

```xml
<efac:UltimateBeneficialOwner>
  <cac:ResidenceAddress>
    <cbc:AdditionalStreetName>Nelson Building</cbc:AdditionalStreetName>
  </cac:ResidenceAddress>
</efac:UltimateBeneficialOwner>
```

```json
{
  "parties": [
    {
      "beneficialOwners": [
        {
          "address": {
            "streetAddress": "2 CheeseStreet, Nelson Building, 2nd floor"
          }
        }
      ]
    }
  ]
}
```

</td>
      </tr>
      <tr id="BT-510(c)-Organization-Company">
        <td class="field break-all">
            <p><b>BT-510(c)-Organization-Company</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/parties.html#_general_structure_of_an_organization_related_information"></a><br>Streetline 2</p><p><i>BT-510:</i> The name of the street, road, avenue, etc., of the organisation's physical address and further identification (e.g. building number).</p>
            <code class="docutils literal notranslate"><span class="pre">/*/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:Organizations/efac:Organization/efac:Company/cac:PostalAddress/cac:AddressLine/cbc:Line</span></code>
        </td>
        <td class="mapping">

<a href="operations.md#get-the-organization-for-a-company">Get the organization for the company</a>, combine the values of `cbc:StreetName`, `cbc:AdditionalStreetName` and each `cac:AddressLine/cbc:Line` in that order, separating each string with ', ' (comma and space) and map to the organization's `address.streetAddress`.

```xml
<efac:Organization>
  <efac:Company>
    <cac:PostalAddress>
      <cac:AddressLine>
        <cbc:Line>3rd Floor</cbc:Line>
      </cac:AddressLine>
    </cac:PostalAddress>
  </efac:Company>
</efac:Organization>
```

```json
{
  "parties": [
    {
      "address": {
        "streetAddress": "2, rue de Europe, Building A, 3rd Floor"
      }
    }
  ]
}
```

</td>
      </tr>
      <tr id="BT-510(c)-Organization-TouchPoint">
        <td class="field break-all">
            <p><b>BT-510(c)-Organization-TouchPoint</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/parties.html#_general_structure_of_an_organization_related_information"></a><br>Streetline 2</p><p><i>BT-510:</i> The name of the street, road, avenue, etc., of the organisation's physical address and further identification (e.g. building number).</p>
            <code class="docutils literal notranslate"><span class="pre">/*/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:Organizations/efac:Organization/efac:TouchPoint/cac:PostalAddress/cac:AddressLine/cbc:Line</span></code>
        </td>
        <td class="mapping">

<a href="operations.md#get-the-organization-for-a-touchpoint">Get the organization for the touchpoint</a>, combine the values of `cbc:StreetName`, `cbc:AdditionalStreetName` and each `cac:AddressLine/cbc:Line` in that order, separating each string with ', ' (comma and space) and map to the organization's `address.streetAddress`.

```xml
<efac:Organization>
  <efac:TouchPoint>
    <cac:PostalAddress>
      <cac:AddressLine>
        <cbc:Line>3rd Floor</cbc:Line>
      </cac:AddressLine>
    </cac:PostalAddress>
  </efac:TouchPoint>
</efac:Organization>
```

```json
{
  "parties": [
    {
      "address": {
        "streetAddress": "2, rue de Europe, Building A, 3rd Floor"
      }
    }
  ]
}
```

</td>
      </tr>
      <tr id="BT-510(c)-UBO">
        <td class="field break-all">
            <p><b>BT-510(c)-UBO</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/parties.html#ultimateBeneficialOwnerSection"></a><br>Streetline 2</p><p><i>BT-510:</i> The name of the street, road, avenue, etc., of the organisation's physical address and further identification (e.g. building number).</p>
            <code class="docutils literal notranslate"><span class="pre">/*/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:Organizations/efac:UltimateBeneficialOwner/cac:ResidenceAddress/cac:AddressLine/cbc:Line</span></code>
        </td>
        <td class="mapping">

<a href="operations.md#get-the-person-for-an-ultimate-beneficial-owner">Get the person for the ultimate beneficial owner</a>, combine the values of `cbc:StreetName`, `cbc:AdditionalStreetName` and each `cac:AddressLine/cbc:Line` in that order, separating each string with ', ' (comma and space) and map to the person's `address.streetAddress`.

```xml
<efac:UltimateBeneficialOwner>
  <cac:ResidenceAddress>
    <cac:AddressLine>
      <cbc:Line>2nd floor</cbc:Line>
    </cac:AddressLine>
  </cac:ResidenceAddress>
</efac:UltimateBeneficialOwner>
```

```json
{
  "parties": [
    {
      "beneficialOwners": [
        {
          "address": {
            "streetAddress": "2 CheeseStreet, Nelson Building, 2nd floor"
          }
        }
      ]
    }
  ]
}
```

</td>
      </tr>
      <tr id="BT-5101(a)-Lot">
        <td class="field break-all">
            <p><b>BT-5101(a)-Lot</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/procedure-lot-part-information.html#performancePlaceSection"></a><br>Place Performance Street</p><p><i>BT-5101:</i> The name of the street, road, avenue, etc., of the place of performance and further identification (e.g. building number).</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='Lot']/cac:ProcurementProject/cac:RealizedLocation/cac:Address/cbc:StreetName</span></code>
        </td>
        <td class="mapping">

This field maps to the same `Address` objects as created for BT-728-Lot, BT-5131-Lot, BT-5121-Lot, BT-5071-Lot, BT-727-Lot, and BT-5141-Lot.

<a href="operations.md#get-the-item-for-a-procurementprojectlot">Get the item for the ProcurementProjectLot</a>.
For each `cac:RealizedLocation`, add or update the corresponding `Address` object in the item's `.deliveryAddresses` array, combine the values of `cbc:StreetName`, `cbc:AdditionalStreetName` and each `cac:AddressLine/cbc:Line` in that order, separating each string with ', ' (comma and space) and map to the address's `.streetAddress`.

```xml
<cac:RealizedLocation>
  <cac:Address>
    <cbc:AdditionalStreetName>Building B1</cbc:AdditionalStreetName>
  </cac:Address>
</cac:RealizedLocation>
```

```json
{
  "tender": {
    "items": [
      {
        "deliveryAddresses": [
          {
            "streetAddress": "Main Street, 2, Building B1, 3rd floor"
          }
        ]
      }
    ]
  }
}
```

</td>
      </tr>
      <tr id="BT-5101(a)-Part">
        <td class="field break-all">
            <p><b>BT-5101(a)-Part</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/procedure-lot-part-information.html#performancePlaceSection"></a><br>Place Performance Street</p><p><i>BT-5101:</i> The name of the street, road, avenue, etc., of the place of performance and further identification (e.g. building number).</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='Part']/cac:ProcurementProject/cac:RealizedLocation/cac:Address/cbc:StreetName</span></code>
        </td>
        <td class="mapping">

This field maps to the same `Address` objects as created for BT-728-Part, BT-5131-Part, BT-5121-Part, BT-5071-Part, BT-727-Part, and BT-5141-Part.
For each `cac:RealizedLocation`, add or update the corresponding `Address` object in the `tender.deliveryAddresses` array, combine the values of `cbc:StreetName`, `cbc:AdditionalStreetName` and each `cac:AddressLine/cbc:Line` in that order, separating each string with ', ' (comma and space) and map to the address's `.streetAddress`.

```xml
<cac:RealizedLocation>
  <cac:Address>
    <cbc:AdditionalStreetName>Building B1</cbc:AdditionalStreetName>
  </cac:Address>
</cac:RealizedLocation>
```

```json
{
  "tender": {
    "deliveryAddresses": [
      {
        "streetAddress": "Main Street, 2, Building B1, 3rd floor"
      }
    ]
  }
}
```

</td>
      </tr>
      <tr id="BT-5101(a)-Procedure">
        <td class="field break-all">
            <p><b>BT-5101(a)-Procedure</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/procedure-lot-part-information.html#performancePlaceSection"></a><br>Place Performance Street</p><p><i>BT-5101:</i> The name of the street, road, avenue, etc., of the place of performance and further identification (e.g. building number).</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProject/cac:RealizedLocation/cac:Address/cbc:StreetName</span></code>
        </td>
        <td class="mapping">

This field maps to the same `Address` objects as created for BT-728-Procedure, BT-5131-Procedure, BT-5121-Procedure, BT-5071-Procedure, BT-727-Procedure, and BT-5141-Procedure.
For each `cac:RealizedLocation`, add or update the corresponding `Address` object in the `tender.deliveryAddresses` array, combine the values of `cbc:StreetName`, `cbc:AdditionalStreetName` and each `cac:AddressLine/cbc:Line` in that order, separating each string with ', ' (comma and space) and map to the address's `.streetAddress`.

```xml
<cac:RealizedLocation>
  <cac:Address>
    <cbc:AdditionalStreetName>Building B1</cbc:AdditionalStreetName>
  </cac:Address>
</cac:RealizedLocation>
```

```json
{
  "tender": {
    "deliveryAddresses": [
      {
        "streetAddress": "Main Street, 2, Building B1, 3rd floor"
      }
    ]
  }
}
```

</td>
      </tr>
      <tr id="BT-5101(b)-Lot">
        <td class="field break-all">
            <p><b>BT-5101(b)-Lot</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/procedure-lot-part-information.html#performancePlaceSection"></a><br>Place Performance Streetline 1</p><p><i>BT-5101:</i> The name of the street, road, avenue, etc., of the place of performance and further identification (e.g. building number).</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='Lot']/cac:ProcurementProject/cac:RealizedLocation/cac:Address/cbc:AdditionalStreetName</span></code>
        </td>
        <td class="mapping">

This field maps to the same `Address` objects as created for BT-728-Lot, BT-5131-Lot, BT-5121-Lot, BT-5071-Lot, BT-727-Lot, and BT-5141-Lot.

<a href="operations.md#get-the-item-for-a-procurementprojectlot">Get the item for the ProcurementProjectLot</a>.
For each `cac:RealizedLocation`, add or update the corresponding `Address` object in the item's `.deliveryAddresses` array, combine the values of `cbc:StreetName`, `cbc:AdditionalStreetName` and each `cac:AddressLine/cbc:Line` in that order, separating each string with ', ' (comma and space) and map to the address's `.streetAddress`.

```xml
<cac:RealizedLocation>
  <cac:Address>
    <cbc:AdditionalStreetName>Building B1</cbc:AdditionalStreetName>
  </cac:Address>
</cac:RealizedLocation>
```

```json
{
  "tender": {
    "deliveryAddresses": [
      {
        "streetAddress": "Main Street, 2, Building B1, 3rd floor"
      }
    ]
  }
}
```

</td>
      </tr>
      <tr id="BT-5101(b)-Part">
        <td class="field break-all">
            <p><b>BT-5101(b)-Part</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/procedure-lot-part-information.html#performancePlaceSection"></a><br>Place Performance Streetline 1</p><p><i>BT-5101:</i> The name of the street, road, avenue, etc., of the place of performance and further identification (e.g. building number).</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='Part']/cac:ProcurementProject/cac:RealizedLocation/cac:Address/cbc:AdditionalStreetName</span></code>
        </td>
        <td class="mapping">

This field maps to the same `Address` objects as created for BT-728-Part, BT-5131-Part, BT-5121-Part, BT-5071-Part, BT-727-Part, and BT-5141-Part.
For each `cac:RealizedLocation`, add or update the corresponding `Address` object in the `tender.deliveryAddresses` array, combine the values of `cbc:StreetName`, `cbc:AdditionalStreetName` and each `cac:AddressLine/cbc:Line` in that order, separating each string with ', ' (comma and space) and map to the address's `.streetAddress`.

```xml
<cac:RealizedLocation>
  <cac:Address>
    <cbc:AdditionalStreetName>Building B1</cbc:AdditionalStreetName>
  </cac:Address>
</cac:RealizedLocation>
```

```json
{
  "tender": {
    "deliveryAddresses": [
      {
        "streetAddress": "Main Street, 2, Building B1, 3rd floor"
      }
    ]
  }
}
```

</td>
      </tr>
      <tr id="BT-5101(b)-Procedure">
        <td class="field break-all">
            <p><b>BT-5101(b)-Procedure</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/procedure-lot-part-information.html#performancePlaceSection"></a><br>Place Performance Streetline 1</p><p><i>BT-5101:</i> The name of the street, road, avenue, etc., of the place of performance and further identification (e.g. building number).</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProject/cac:RealizedLocation/cac:Address/cbc:AdditionalStreetName</span></code>
        </td>
        <td class="mapping">

This field maps to the same `Address` objects as created for BT-728-Procedure, BT-5131-Procedure, BT-5121-Procedure, BT-5071-Procedure, BT-727-Procedure, and BT-5141-Procedure.
For each `cac:RealizedLocation`, add or update the corresponding `Address` object in the `tender.deliveryAddresses` array, combine the values of `cbc:StreetName`, `cbc:AdditionalStreetName` and each `cac:AddressLine/cbc:Line` in that order, separating each string with ', ' (comma and space) and map to the address's `.streetAddress`.

```xml
<cac:RealizedLocation>
  <cac:Address>
    <cbc:AdditionalStreetName>Building B1</cbc:AdditionalStreetName>
  </cac:Address>
</cac:RealizedLocation>
```

```json
{
  "tender": {
    "deliveryAddresses": [
      {
        "streetAddress": "Main Street, 2, Building B1, 3rd floor"
      }
    ]
  }
}
```

</td>
      </tr>
      <tr id="BT-5101(c)-Lot">
        <td class="field break-all">
            <p><b>BT-5101(c)-Lot</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/procedure-lot-part-information.html#performancePlaceSection"></a><br>Place Performance Streetline 2</p><p><i>BT-5101:</i> The name of the street, road, avenue, etc., of the place of performance and further identification (e.g. building number).</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='Lot']/cac:ProcurementProject/cac:RealizedLocation/cac:Address/cac:AddressLine/cbc:Line</span></code>
        </td>
        <td class="mapping">

This field maps to the same `Address` objects as created for BT-728-Lot, BT-5131-Lot, BT-5121-Lot, BT-5071-Lot, BT-727-Lot, and BT-5141-Lot.

<a href="operations.md#get-the-item-for-a-procurementprojectlot">Get the item for the ProcurementProjectLot</a>.
For each `cac:RealizedLocation`, add or update the corresponding `Address` object in the item's `.deliveryAddresses` array, combine the values of `cbc:StreetName`, `cbc:AdditionalStreetName` and each `cac:AddressLine/cbc:Line` in that order, separating each string with ', ' (comma and space) and map to the address's `.streetAddress`.

```xml
<cac:RealizedLocation>
  <cac:Address>
    <cbc:AdditionalStreetName>Building B1</cbc:AdditionalStreetName>
  </cac:Address>
</cac:RealizedLocation>
```

```json
{
  "tender": {
    "items": [
      {
        "deliveryAddresses": [
          {
            "streetAddress": "Main Street, 2, Building B1, 3rd floor"
          }
        ]
      }
    ]
  }
}
```

</td>
      </tr>
      <tr id="BT-5101(c)-Part">
        <td class="field break-all">
            <p><b>BT-5101(c)-Part</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/procedure-lot-part-information.html#performancePlaceSection"></a><br>Place Performance Streetline 2</p><p><i>BT-5101:</i> The name of the street, road, avenue, etc., of the place of performance and further identification (e.g. building number).</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='Part']/cac:ProcurementProject/cac:RealizedLocation/cac:Address/cac:AddressLine/cbc:Line</span></code>
        </td>
        <td class="mapping">

This field maps to the same `Address` objects as created for BT-728-Part, BT-5131-Part, BT-5121-Part, BT-5071-Part, BT-727-Part, and BT-5141-Part.
For each `cac:RealizedLocation`, add or update the corresponding `Address` object in the `tender.deliveryAddresses` array, combine the values of `cbc:StreetName`, `cbc:AdditionalStreetName` and each `cac:AddressLine/cbc:Line` in that order, separating each string with ', ' (comma and space) and map to the address's `.streetAddress`.

```xml
<cac:RealizedLocation>
  <cac:Address>
    <cbc:AdditionalStreetName>Building B1</cbc:AdditionalStreetName>
  </cac:Address>
</cac:RealizedLocation>
```

```json
{
  "tender": {
    "deliveryAddresses": [
      {
        "streetAddress": "Main Street, 2, Building B1, 3rd floor"
      }
    ]
  }
}
```

</td>
      </tr>
      <tr id="BT-5101(c)-Procedure">
        <td class="field break-all">
            <p><b>BT-5101(c)-Procedure</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/procedure-lot-part-information.html#performancePlaceSection"></a><br>Place Performance Streetline 2</p><p><i>BT-5101:</i> The name of the street, road, avenue, etc., of the place of performance and further identification (e.g. building number).</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProject/cac:RealizedLocation/cac:Address/cac:AddressLine/cbc:Line</span></code>
        </td>
        <td class="mapping">

This field maps to the same `Address` objects as created for BT-728-Procedure, BT-5131-Procedure, BT-5121-Procedure, BT-5071-Procedure, BT-727-Procedure, and BT-5141-Procedure.
For each `cac:RealizedLocation`, add or update the corresponding `Address` object in the `tender.deliveryAddresses` array, combine the values of `cbc:StreetName`, `cbc:AdditionalStreetName` and each `cac:AddressLine/cbc:Line` in that order, separating each string with ', ' (comma and space) and map to the address's `.streetAddress`.

```xml
<cac:RealizedLocation>
  <cac:Address>
    <cbc:AdditionalStreetName>Building B1</cbc:AdditionalStreetName>
  </cac:Address>
</cac:RealizedLocation>
```

```json
{
  "tender": {
    "deliveryAddresses": [
      {
        "streetAddress": "Main Street, 2, Building B1, 3rd floor"
      }
    ]
  }
}
```

</td>
      </tr>
      <tr id="BT-512-Organization-Company">
        <td class="field break-all">
            <p><b>BT-512-Organization-Company</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/parties.html#_general_structure_of_an_organization_related_information"></a><br>Organisation Post Code</p><p><i>BT-512:</i> The post code of the organisation's physical address.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:Organizations/efac:Organization/efac:Company/cac:PostalAddress/cbc:PostalZone</span></code>
        </td>
        <td class="mapping">

<a href="operations.md#get-the-organization-for-a-company">Get the organization for the company</a> and map to the organization's `.address.postalCode`

```xml
<efac:Organization>
  <efac:Company>
    <cac:PostalAddress>
      <cbc:PostalZone>2345</cbc:PostalZone>
    </cac:PostalAddress>
  </efac:Company>
</efac:Organization>
```

```json
{
  "parties": [
    {
      "address": {
        "postalCode": "2345"
      }
    }
  ]
}
```

</td>
      </tr>
      <tr id="BT-512-Organization-TouchPoint">
        <td class="field break-all">
            <p><b>BT-512-Organization-TouchPoint</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/parties.html#_general_structure_of_an_organization_related_information"></a><br>Post Code</p><p><i>BT-512:</i> The post code of the organisation's physical address.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:Organizations/efac:Organization/efac:TouchPoint/cac:PostalAddress/cbc:PostalZone</span></code>
        </td>
        <td class="mapping">

<a href="operations.md#get-the-organization-for-a-touchpoint">Get the organization for the touchpoint</a> and map to the touchpoint's `.address.postalCode`

```xml
<efac:Organization>
  <efac:TouchPoint>
    <cac:PostalAddress>
      <cbc:PostalZone>2345</cbc:PostalZone>
    </cac:PostalAddress>
  </efac:TouchPoint>
</efac:Organization>
```

```json
{
  "parties": [
    {
      "address": {
        "postalCode": "2345"
      }
    }
  ]
}
```

</td>
      </tr>
      <tr id="BT-512-UBO">
        <td class="field break-all">
            <p><b>BT-512-UBO</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/parties.html#ultimateBeneficialOwnerSection"></a><br>Post Code</p><p><i>BT-512:</i> The post code of the organisation's physical address.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:Organizations/efac:UltimateBeneficialOwner/cac:ResidenceAddress/cbc:PostalZone</span></code>
        </td>
        <td class="mapping">

<a href="operations.md#get-the-person-for-an-ultimate-beneficial-owner">Get the person for the ultimate beneficial owner</a> and map to the person's `.address.postalCode`.

```xml
<efac:UltimateBeneficialOwner>
  <cac:ResidenceAddress>
    <cbc:PostalZone>C6HA782</cbc:PostalZone>
  </cac:ResidenceAddress>
</efac:UltimateBeneficialOwner>
```

```json
{
  "parties": [
    {
      "beneficialOwners": [
        {
          "address": {
            "postalCode": "C6HA78"
          }
        }
      ]
    }
  ]
}
```

</td>
      </tr>
      <tr id="BT-5121-Lot">
        <td class="field break-all">
            <p><b>BT-5121-Lot</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/procedure-lot-part-information.html#performancePlaceSection"></a><br>Place Performance Post Code</p><p><i>BT-5121:</i> The postcode of the place of performance.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='Lot']/cac:ProcurementProject/cac:RealizedLocation/cac:Address/cbc:PostalZone</span></code>
        </td>
        <td class="mapping">

This field maps to the same `Address` objects as created for BT-728-Lot, BT-5131-Lot, BT-5071-Lot, BT-727-Lot, BT-5101-Lot and BT-5141-Lot.

<a href="operations.md#get-the-item-for-a-procurementprojectlot">Get the item for the ProcurementProjectLot</a>.
For each `cac:RealizedLocation`, add or update the corresponding `Address` object in the item's `.deliveryAddresses` array and map to its `.postalCode`.

```xml
<cac:RealizedLocation>
  <cac:Address>
    <cbc:PostalZone>XY14 2LG</cbc:PostalZone>
  </cac:Address>
</cac:RealizedLocation>
```

```json
{
  "tender": {
    "items": [
      {
        "deliveryAddresses": [
          {
            "postalCode": "XY14 2LG"
          }
        ]
      }
    ]
  }
}
```

</td>
      </tr>
      <tr id="BT-5121-Part">
        <td class="field break-all">
            <p><b>BT-5121-Part</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/procedure-lot-part-information.html#performancePlaceSection"></a><br>Place Performance Post Code</p><p><i>BT-5121:</i> The postcode of the place of performance.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='Part']/cac:ProcurementProject/cac:RealizedLocation/cac:Address/cbc:PostalZone</span></code>
        </td>
        <td class="mapping">

This field maps to the same `Address` objects as created for BT-728-Part, BT-5131-Part, BT-5071-Part, BT-727-Part, BT-5101-Part and BT-5141-Part.
For each `cac:RealizedLocation`, add or update the corresponding `Address` object in the `tender.deliveryAddresses` array and map to its `.postalCode`.

```xml
<cac:RealizedLocation>
  <cac:Address>
    <cbc:PostalZone>XY14 2LG</cbc:PostalZone>
  </cac:Address>
</cac:RealizedLocation>
```

```json
{
  "tender": {
    "deliveryAddresses": [
      {
        "postalCode": "XY14 2LG"
      }
    ]
  }
}
```

</td>
      </tr>
      <tr id="BT-5121-Procedure">
        <td class="field break-all">
            <p><b>BT-5121-Procedure</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/procedure-lot-part-information.html#performancePlaceSection"></a><br>Place Performance Post Code</p><p><i>BT-5121:</i> The postcode of the place of performance.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProject/cac:RealizedLocation/cac:Address/cbc:PostalZone</span></code>
        </td>
        <td class="mapping">

This field maps to the same `Address` objects as created for BT-728-Procedure, BT-5131-Procedure, BT-5071-Procedure, BT-727-Procedure, BT-5101-Procedure and BT-5141-Procedure.
For each `cac:RealizedLocation`, add or update the corresponding `Address` object in the `tender.deliveryAddresses` array and map to its `.postalCode`.

```xml
<cac:RealizedLocation>
  <cac:Address>
    <cbc:PostalZone>XY14 2LG</cbc:PostalZone>
  </cac:Address>
</cac:RealizedLocation>
```

```json
{
  "tender": {
    "deliveryAddresses": [
      {
        "postalCode": "XY14 2LG"
      }
    ]
  }
}
```

</td>
      </tr>
      <tr id="BT-513-Organization-Company">
        <td class="field break-all">
            <p><b>BT-513-Organization-Company</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/parties.html#_general_structure_of_an_organization_related_information"></a><br>Organisation City</p><p><i>BT-513:</i> The name of the locality (city, town, or village) of the organisation's physical address.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:Organizations/efac:Organization/efac:Company/cac:PostalAddress/cbc:CityName</span></code>
        </td>
        <td class="mapping">

<a href="operations.md#get-the-organization-for-a-company">Get the organization for the company</a> and map to the organization's `.address.locality`.

```xml
<efac:Organization>
  <efac:Company>
    <cac:PostalAddress>
      <cbc:CityName>SmallCity</cbc:CityName>
    </cac:PostalAddress>
  </efac:Company>
</efac:Organization>
```

```json
{
  "parties": [
    {
      "address": {
        "locality": "SmallCity"
      }
    }
  ]
}
```

</td>
      </tr>
      <tr id="BT-513-Organization-TouchPoint">
        <td class="field break-all">
            <p><b>BT-513-Organization-TouchPoint</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/parties.html#_general_structure_of_an_organization_related_information"></a><br>City</p><p><i>BT-513:</i> The name of the locality (city, town, or village) of the organisation's physical address.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:Organizations/efac:Organization/efac:TouchPoint/cac:PostalAddress/cbc:CityName</span></code>
        </td>
        <td class="mapping">

<a href="operations.md#get-the-organization-for-a-touchpoint">Get the organization for the touchpoint</a> and map to the organization's `.address.locality`.

```xml
<efac:Organization>
  <efac:TouchPoint>
    <cac:PostalAddress>
      <cbc:CityName>SmallCity</cbc:CityName>
    </cac:PostalAddress>
  </efac:TouchPoint>
</efac:Organization>
```

```json
{
  "parties": [
    {
      "address": {
        "locality": "SmallCity"
      }
    }
  ]
}
```

</td>
      </tr>
      <tr id="BT-513-UBO">
        <td class="field break-all">
            <p><b>BT-513-UBO</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/parties.html#ultimateBeneficialOwnerSection"></a><br>City</p><p><i>BT-513:</i> The name of the locality (city, town, or village) of the organisation's physical address.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:Organizations/efac:UltimateBeneficialOwner/cac:ResidenceAddress/cbc:CityName</span></code>
        </td>
        <td class="mapping">

<a href="operations.md#get-the-person-for-an-ultimate-beneficial-owner">Get the person for the ultimate beneficial owner</a> and map to the person's `.address.postalCode`.

```xml
<efac:UltimateBeneficialOwner>
  <cac:ResidenceAddress>
    <cbc:CityName>MouseTown</cbc:CityName>
  </cac:ResidenceAddress>
</efac:UltimateBeneficialOwner>
```

```json
{
  "parties": [
    {
      "beneficialOwners": [
        {
          "address": {
            "locality": "MouseTown"
          }
        }
      ]
    }
  ]
}
```

</td>
      </tr>
      <tr id="BT-5131-Lot">
        <td class="field break-all">
            <p><b>BT-5131-Lot</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/procedure-lot-part-information.html#performancePlaceSection"></a><br>Place Performance City</p><p><i>BT-5131:</i> The name of the locality (city, town, or village) of the place of performance.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='Lot']/cac:ProcurementProject/cac:RealizedLocation/cac:Address/cbc:CityName</span></code>
        </td>
        <td class="mapping">

This field maps to the same `Address` objects as created for BT-728-Lot, BT-5121-Lot, BT-5071-Lot, BT-727-Lot, BT-5101-Lot and BT-5141-Lot.

<a href="operations.md#get-the-item-for-a-procurementprojectlot">Get the item for the ProcurementProjectLot</a>.
For each `cac:RealizedLocation`, add or update the corresponding `Address` object in the item's `.deliveryAddresses` array and map to its `.locality`.

```xml
<cac:RealizedLocation>
  <cac:Address>
    <cbc:CityName>BigCity</cbc:CityName>
  </cac:Address>
</cac:RealizedLocation>
```

```json
{
  "tender": {
    "items": [
      {
        "deliveryAddresses": [
          {
            "locality": "BigCity"
          }
        ]
      }
    ]
  }
}
```

</td>
      </tr>
      <tr id="BT-5131-Part">
        <td class="field break-all">
            <p><b>BT-5131-Part</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/procedure-lot-part-information.html#performancePlaceSection"></a><br>Place Performance City</p><p><i>BT-5131:</i> The name of the locality (city, town, or village) of the place of performance.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='Part']/cac:ProcurementProject/cac:RealizedLocation/cac:Address/cbc:CityName</span></code>
        </td>
        <td class="mapping">

This field maps to the same `Address` objects as created for BT-728-Part, BT-5121-Part, BT-5071-Part, BT-727-Part, BT-5101-Part and BT-5141-Part.
For each `cac:RealizedLocation`, add or update the corresponding `Address` object in the `tender.deliveryAddresses` array and map to its `.locality`.

```xml
<cac:RealizedLocation>
  <cac:Address>
    <cbc:CityName>BigCity</cbc:CityName>
  </cac:Address>
</cac:RealizedLocation>
```

```json
{
  "tender": {
    "deliveryAddresses": [
      {
        "locality": "BigCity"
      }
    ]
  }
}
```

</td>
      </tr>
      <tr id="BT-5131-Procedure">
        <td class="field break-all">
            <p><b>BT-5131-Procedure</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/procedure-lot-part-information.html#performancePlaceSection"></a><br>Place Performance City</p><p><i>BT-5131:</i> The name of the locality (city, town, or village) of the place of performance.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProject/cac:RealizedLocation/cac:Address/cbc:CityName</span></code>
        </td>
        <td class="mapping">

This field maps to the same `Address` objects as created for BT-728-Procedure, BT-5121-Procedure, BT-5071-Procedure, BT-727-Procedure, BT-5101-Procedure and BT-5141-Procedure.
For each `cac:RealizedLocation`, add or update the corresponding `Address` object in the `tender.deliveryAddresses` array and map to its `.locality`.

```xml
<cac:RealizedLocation>
  <cac:Address>
    <cbc:CityName>BigCity</cbc:CityName>
  </cac:Address>
</cac:RealizedLocation>
```

```json
{
  "tender": {
    "deliveryAddresses": [
      {
        "locality": "BigCity"
      }
    ]
  }
}
```

</td>
      </tr>
      <tr id="BT-514-Organization-Company">
        <td class="field break-all">
            <p><b>BT-514-Organization-Company</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/parties.html#_general_structure_of_an_organization_related_information"></a><br>Organisation Country Code</p><p><i>BT-514:</i> The country of the organisation's physical address.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:Organizations/efac:Organization/efac:Company/cac:PostalAddress/cac:Country/cbc:IdentificationCode</span></code>
        </td>
        <td class="mapping">

<a href="operations.md#get-the-organization-for-a-company">Get the organization for the company</a>, look up the equivalent ISO 3166-1 alpha-2 code in the <a href="https://op.europa.eu/en/web/eu-vocabularies/concept-scheme/-/resource?uri=http://publications.europa.eu/resource/authority/country">authority table</a> and map to the organization's `.address.country`.

```xml
<efac:Organization>
  <efac:Company>
    <cac:PostalAddress>
      <cac:Country>
        <cbc:IdentificationCode listName="eforms-country">GBR</cbc:IdentificationCode>
      </cac:Country>
    </cac:PostalAddress>
  </efac:Company>
</efac:Organization>
```

```json
{
  "parties": [
    {
      "address": {
        "country": "GB"
      }
    }
  ]
}
```

</td>
      </tr>
      <tr id="BT-514-Organization-TouchPoint">
        <td class="field break-all">
            <p><b>BT-514-Organization-TouchPoint</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/parties.html#_general_structure_of_an_organization_related_information"></a><br>Country Code</p><p><i>BT-514:</i> The country of the organisation's physical address.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:Organizations/efac:Organization/efac:TouchPoint/cac:PostalAddress/cac:Country/cbc:IdentificationCode</span></code>
        </td>
        <td class="mapping">

<a href="operations.md#get-the-organization-for-a-touchpoint">Get the organization for the touchpoint</a>, look up the equivalent ISO 3166-1 alpha-2 code in the <a href="https://op.europa.eu/en/web/eu-vocabularies/concept-scheme/-/resource?uri=http://publications.europa.eu/resource/authority/country">authority table</a> and map to the organization's `.address.country`.

```xml
<efac:Organization>
  <efac:TouchPoint>
    <cac:PostalAddress>
      <cac:Country>
        <cbc:IdentificationCode listName="eforms-country">GBR</cbc:IdentificationCode>
      </cac:Country>
    </cac:PostalAddress>
  </efac:TouchPoint>
</efac:Organization>
```

```json
{
  "parties": [
    {
      "address": {
        "country": "GB"
      }
    }
  ]
}
```

</td>
      </tr>
      <tr id="BT-514-UBO">
        <td class="field break-all">
            <p><b>BT-514-UBO</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/parties.html#ultimateBeneficialOwnerSection"></a><br>Country Code</p><p><i>BT-514:</i> The country of the organisation's physical address.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:Organizations/efac:UltimateBeneficialOwner/cac:ResidenceAddress/cac:Country/cbc:IdentificationCode</span></code>
        </td>
        <td class="mapping">

<a href="operations.md#get-the-person-for-an-ultimate-beneficial-owner">Get the person for the ultimate beneficial owner</a>, look up the equivalent ISO 3166-1 alpha-2 code in the <a href="https://op.europa.eu/en/web/eu-vocabularies/concept-scheme/-/resource?uri=http://publications.europa.eu/resource/authority/country">authority table</a> and map to the person's `.address.country`.

```xml
<efac:UltimateBeneficialOwner>
  <cac:ResidenceAddress>
    <cac:Country>
      <cbc:IdentificationCode listName="eforms-country">GBR</cbc:IdentificationCode>
    </cac:Country>
  </cac:ResidenceAddress>
</efac:UltimateBeneficialOwner>
```

```json
{
  "parties": [
    {
      "beneficialOwners": [
        {
          "address": {
            "country": "GB"
          }
        }
      ]
    }
  ]
}
```

</td>
      </tr>
      <tr id="BT-5141-Lot">
        <td class="field break-all">
            <p><b>BT-5141-Lot</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/procedure-lot-part-information.html#performancePlaceSection"></a><br>Place Performance Country Code</p><p><i>BT-5141:</i> The country of the place of performance.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='Lot']/cac:ProcurementProject/cac:RealizedLocation/cac:Address/cac:Country/cbc:IdentificationCode</span></code>
        </td>
        <td class="mapping">

This field maps to the same `Address` objects as created for BT-728-Lot, BT-5131-Lot, BT-5121-Lot, BT-5071-Lot, BT-727-Lot, and BT-5101-Lot.

<a href="operations.md#get-the-item-for-a-procurementprojectlot">Get the item for the ProcurementProjectLot</a>.
For each `cac:RealizedLocation`, add or update the corresponding `Address` object in the item's `.deliveryAddresses` array, look up the equivalent ISO 3166-1 alpha-2 code in the <a href="https://op.europa.eu/en/web/eu-vocabularies/concept-scheme/-/resource?uri=http://publications.europa.eu/resource/authority/country">authority table</a> and map to the address's `.country`.

```xml
<cac:RealizedLocation>
  <cac:Address>
    <cac:Country>
      <cbc:IdentificationCode listName="eforms-country">GBR</cbc:IdentificationCode>
    </cac:Country>
  </cac:Address>
</cac:RealizedLocation>
```

```json
{
  "tender": {
    "items": [
      {
        "deliveryAddresses": [
          {
            "country": "GB"
          }
        ]
      }
    ]
  }
}
```

</td>
      </tr>
      <tr id="BT-5141-Part">
        <td class="field break-all">
            <p><b>BT-5141-Part</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/procedure-lot-part-information.html#performancePlaceSection"></a><br>Place Performance Country Code</p><p><i>BT-5141:</i> The country of the place of performance.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='Part']/cac:ProcurementProject/cac:RealizedLocation/cac:Address/cac:Country/cbc:IdentificationCode</span></code>
        </td>
        <td class="mapping">

This field maps to the same `Address` objects as created for BT-728-Part, BT-5131-Part, BT-5121-Part, BT-5071-Part, BT-727-Part, and BT-5101-Part.
For each `cac:RealizedLocation`, add or update the corresponding `Address` object in the `tender.deliveryAddresses` array, look up the equivalent ISO 3166-1 alpha-2 code in the <a href="https://op.europa.eu/en/web/eu-vocabularies/concept-scheme/-/resource?uri=http://publications.europa.eu/resource/authority/country">authority table</a> and map to the address's `.country`.

```xml
<cac:RealizedLocation>
  <cac:Address>
    <cac:Country>
      <cbc:IdentificationCode listName="eforms-country">GBR</cbc:IdentificationCode>
    </cac:Country>
  </cac:Address>
</cac:RealizedLocation>
```

```json
{
  "tender": {
    "deliveryAddresses": [
      {
        "country": "GB"
      }
    ]
  }
}
```

</td>
      </tr>
      <tr id="BT-5141-Procedure">
        <td class="field break-all">
            <p><b>BT-5141-Procedure</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/procedure-lot-part-information.html#performancePlaceSection"></a><br>Place Performance Country Code</p><p><i>BT-5141:</i> The country of the place of performance.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProject/cac:RealizedLocation/cac:Address/cac:Country/cbc:IdentificationCode</span></code>
        </td>
        <td class="mapping">

This field maps to the same `Address` objects as created for BT-728-Procedure, BT-5131-Procedure, BT-5121-Procedure, BT-5071-Procedure, BT-727-Procedure, and BT-5101-Procedure.
For each `cac:RealizedLocation`, add or update the corresponding `Address` object in the `tender.deliveryAddresses` array, look up the equivalent ISO 3166-1 alpha-2 code in the <a href="https://op.europa.eu/en/web/eu-vocabularies/concept-scheme/-/resource?uri=http://publications.europa.eu/resource/authority/country">authority table</a> and map to the address's `.country`.

```xml
<cac:RealizedLocation>
  <cac:Address>
    <cac:Country>
      <cbc:IdentificationCode listName="eforms-country">GBR</cbc:IdentificationCode>
    </cac:Country>
  </cac:Address>
</cac:RealizedLocation>
```

```json
{
  "tender": {
    "deliveryAddresses": [
      {
        "country": "GB"
      }
    ]
  }
}
```

</td>
      </tr>
      <tr id="BT-52-Lot">
        <td class="field break-all">
            <p><b>BT-52-Lot</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/procedure-lot-part-information.html#successiveReductionSection"></a><br>Successive Reduction Indicator (Lot)</p><p><i>BT-52:</i> The procedure will take place in successive stages. In each stage, some participants may be eliminated.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='Lot']/cac:TenderingProcess/cbc:CandidateReductionConstraintIndicator</span></code>
        </td>
        <td class="mapping">

<a href="operations.md#get-the-lot-for-a-procurementprojectlot">Get the lot for the ProcurementProjectLot</a> and set its `secondStage.successiveReduction` to `true`.

```xml
<cbc:CandidateReductionConstraintIndicator>true</cbc:CandidateReductionConstraintIndicator>
```

```json
{
  "tender": {
    "lots": [
      {
        "secondStage": {
          "successiveReduction": true
        }
      }
    ]
  }
}
```

</td>
      </tr>
      <tr id="BT-531-Lot">
        <td class="field break-all">
            <p><b>BT-531-Lot</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/procedure-lot-part-information.html#natureSection"></a><br>Additional Nature (different from Main)</p><p><i>BT-531:</i> The nature (e.g. services) of what is being bought, additional to Main Nature.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='Lot']/cac:ProcurementProject/cac:ProcurementAdditionalType/cbc:ProcurementTypeCode[@listName='contract-nature']</span></code>
        </td>
        <td class="mapping">

<a href="operations.md#get-the-lot-for-a-procurementprojectlot">Get the lot for the ProcurementProjectLot</a> and add to its `.additionalProcurementCategories` array.

```xml
<cac:ProcurementAdditionalType>
  <cbc:ProcurementTypeCode listName="contract-nature">works</cbc:ProcurementTypeCode>
</cac:ProcurementAdditionalType>
```

```json
{
  "tender": {
    "lots": [
      {
        "additionalProcurementCategories": [
          "works"
        ]
      }
    ]
  }
}
```

</td>
      </tr>
      <tr id="BT-531-Part">
        <td class="field break-all">
            <p><b>BT-531-Part</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/procedure-lot-part-information.html#natureSection"></a><br>Additional Nature (different from Main)</p><p><i>BT-531:</i> The nature (e.g. services) of what is being bought, additional to Main Nature.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='Part']/cac:ProcurementProject/cac:ProcurementAdditionalType/cbc:ProcurementTypeCode[@listName='contract-nature']</span></code>
        </td>
        <td class="mapping">

Add to `tender.additionalProcurementCategories` array.

```xml
<cac:ProcurementAdditionalType>
  <cbc:ProcurementTypeCode listName="contract-nature">works</cbc:ProcurementTypeCode>
</cac:ProcurementAdditionalType>
```

```json
{
  "tender": {
    "additionalProcurementCategories": [
      "works"
    ]
  }
}
```

</td>
      </tr>
      <tr id="BT-531-Procedure">
        <td class="field break-all">
            <p><b>BT-531-Procedure</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/procedure-lot-part-information.html#natureSection"></a><br>Additional Nature (different from Main)</p><p><i>BT-531:</i> The nature (e.g. services) of what is being bought, additional to Main Nature.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProject/cac:ProcurementAdditionalType/cbc:ProcurementTypeCode[not(@listName='transport-service')]</span></code>
        </td>
        <td class="mapping">

Add to `tender.additionalProcurementCategories` array.

```xml
<cac:ProcurementAdditionalType>
  <cbc:ProcurementTypeCode listName="contract-nature">works</cbc:ProcurementTypeCode>
</cac:ProcurementAdditionalType>
```

```json
{
  "tender": {
    "additionalProcurementCategories": [
      "works"
    ]
  }
}
```

</td>
      </tr>
      <tr id="BT-536-Lot">
        <td class="field break-all">
            <p><b>BT-536-Lot</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/procedure-lot-part-information.html#plannedPeriodSection"></a><br>Duration Start Date</p><p><i>BT-536:</i> The (estimated) date when the contract, framework agreement, dynamic purchasing system or qualification system will start.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='Lot']/cac:ProcurementProject/cac:PlannedPeriod/cbc:StartDate</span></code>
        </td>
        <td class="mapping">

<a href="operations.md#get-the-lot-for-a-procurementprojectlot">Get the lot for the ProcurementProjectLot</a>, <a href="operations.md#convert-a-date-to-iso-format">convert date to ISO format</a> and map to the lot's `.contractPeriod.startDate`.

```xml
<cac:PlannedPeriod>
  <cbc:StartDate>2019-11-15+01:00</cbc:StartDate>
</cac:PlannedPeriod>
```

```json
{
  "tender": {
    "lots": [
      {
        "contractPeriod": {
          "startDate": "2019-11-15T00:00:00+01:00"
        }
      }
    ]
  }
}
```

</td>
      </tr>
      <tr id="BT-536-Part">
        <td class="field break-all">
            <p><b>BT-536-Part</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/procedure-lot-part-information.html#plannedPeriodSection"></a><br>Duration Start Date</p><p><i>BT-536:</i> The (estimated) date when the contract, framework agreement, dynamic purchasing system or qualification system will start.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='Part']/cac:ProcurementProject/cac:PlannedPeriod/cbc:StartDate</span></code>
        </td>
        <td class="mapping">

<a href="operations.md#convert-a-date-to-iso-format">Convert date to ISO format</a> and map to `tender.contractPeriod.startDate`.

```xml
<cac:PlannedPeriod>
  <cbc:StartDate>2019-11-15+01:00</cbc:StartDate>
</cac:PlannedPeriod>
```

```json
{
  "tender": {
    "contractPeriod": {
      "startDate": "2019-11-15T00:00:00+01:00"
    }
  }
}
```

</td>
      </tr>
      <tr id="BT-537-Lot">
        <td class="field break-all">
            <p><b>BT-537-Lot</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/procedure-lot-part-information.html#plannedPeriodSection"></a><br>Duration End Date</p><p><i>BT-537:</i> The (estimated) date when the contract, framework agreement, dynamic purchasing system or qualification system will finish.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='Lot']/cac:ProcurementProject/cac:PlannedPeriod/cbc:EndDate</span></code>
        </td>
        <td class="mapping">

<a href="operations.md#get-the-lot-for-a-procurementprojectlot">Get the lot for the ProcurementProjectLot</a>, <a href="operations.md#convert-a-date-to-iso-format">convert date to ISO format</a> and map to the lot's `.contractPeriod.endDate`.

```xml
<cac:PlannedPeriod>
  <cbc:EndDate>2019-11-19+01:00</cbc:EndDate>
</cac:PlannedPeriod>
```

```json
{
  "tender": {
    "lots": [
      {
        "contractPeriod": {
          "endDate": "2019-11-19T23:59:59+01:00"
        }
      }
    ]
  }
}
```

</td>
      </tr>
      <tr id="BT-537-Part">
        <td class="field break-all">
            <p><b>BT-537-Part</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/procedure-lot-part-information.html#plannedPeriodSection"></a><br>Duration End Date</p><p><i>BT-537:</i> The (estimated) date when the contract, framework agreement, dynamic purchasing system or qualification system will finish.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='Part']/cac:ProcurementProject/cac:PlannedPeriod/cbc:EndDate</span></code>
        </td>
        <td class="mapping">

<a href="operations.md#convert-a-date-to-iso-format">Convert date to ISO format</a> and map to `tender.contractPeriod.endDate`.

```xml
<cac:PlannedPeriod>
  <cbc:EndDate>2019-11-19+01:00</cbc:EndDate>
</cac:PlannedPeriod>
```

```json
{
  "tender": {
    "contractPeriod": {
      "endDate": "2019-11-19T23:59:59+01:00"
    }
  }
}
```

</td>
      </tr>
      <tr id="BT-538-Lot">
        <td class="field break-all">
            <p><b>BT-538-Lot</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/procedure-lot-part-information.html#plannedPeriodSection"></a><br>Duration Other</p><p><i>BT-538:</i> The duration is unknown, unlimited, etc.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='Lot']/cac:ProcurementProject/cac:PlannedPeriod/cbc:DescriptionCode</span></code>
        </td>
        <td class="mapping">

<a href="operations.md#get-the-lot-for-a-procurementprojectlot">Get the lot for the ProcurementProjectLot</a> and map to its `.contractPeriod.description`.

```xml
<cac:PlannedPeriod>
  <cbc:DescriptionCode listName="timeperiod">UNLIMITED</cbc:DescriptionCode>
</cac:PlannedPeriod>
```

```json
{
  "tender": {
    "lots": [
      {
        "contractPeriod": {
          "description": "unknown"
        }
      }
    ]
  }
}
```

</td>
      </tr>
      <tr id="BT-538-Part">
        <td class="field break-all">
            <p><b>BT-538-Part</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/procedure-lot-part-information.html#plannedPeriodSection"></a><br>Duration Other</p><p><i>BT-538:</i> The duration is unknown, unlimited, etc.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='Part']/cac:ProcurementProject/cac:PlannedPeriod/cbc:DescriptionCode</span></code>
        </td>
        <td class="mapping">

Map to `tender.contractPeriod.description`

```xml
<cac:PlannedPeriod>
  <cbc:DescriptionCode listName="timeperiod">UNLIMITED</cbc:DescriptionCode>
</cac:PlannedPeriod>
```

```json
{
  "tender": {
    "contractPeriod": {
      "description": "unknown"
    }
  }
}
```

</td>
      </tr>
      <tr id="BT-539-Lot">
        <td class="field break-all">
            <p><b>BT-539-Lot</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/procedure-lot-part-information.html#awardCriteriaSection"></a><br>Award Criterion Type</p><p><i>BT-539:</i> Whether the criterion concerns the price, the cost, or a non-price non-cost attribute of the tender. (Price is the acquisition price; cost is any other non-price monetary criterion.)</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='Lot']/cac:TenderingTerms/cac:AwardingTerms/cac:AwardingCriterion/cac:SubordinateAwardingCriterion/cbc:AwardingCriterionTypeCode[@listName='award-criterion-type']</span></code>
        </td>
        <td class="mapping">

This field maps to the same `AwardCriterion` objects as created for BT-540-Lot, BT-541-Lot, BT-5421-Lot, BT-5422-Lot, BT-5423-Lot and BT-734-Lot.

<a href="operations.md#get-the-lot-for-a-procurementprojectlot">Get the lot for the ProcurementProjectLot</a>.
For each `cac:SubordinateAwardingCriterion`, add or update a corresponding `AwardCriterion` in the lot's `.awardCriteria.criteria` array and map to the award critereon's `.type`.

```xml
<cac:SubordinateAwardingCriterion>
  <cbc:AwardingCriterionTypeCode listName="award-criterion-type">quality</cbc:AwardingCriterionTypeCode>
</cac:SubordinateAwardingCriterion>
```

```json
{
  "tender": {
    "lots": [
      {
        "awardCriteria": {
          "criteria": [
            {
              "type": "quality"
            }
          ]
        }
      }
    ]
  }
}
```

</td>
      </tr>
      <tr id="BT-539-LotsGroup">
        <td class="field break-all">
            <p><b>BT-539-LotsGroup</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/procedure-lot-part-information.html#awardCriteriaSection"></a><br>Award Criterion Type</p><p><i>BT-539:</i> Whether the criterion concerns the price, the cost, or a non-price non-cost attribute of the tender. (Price is the acquisition price; cost is any other non-price monetary criterion.)</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='LotsGroup']/cac:TenderingTerms/cac:AwardingTerms/cac:AwardingCriterion/cac:SubordinateAwardingCriterion/cbc:AwardingCriterionTypeCode[@listName='award-criterion-type']</span></code>
        </td>
        <td class="mapping">

This field maps to the same `AwardCriterion` objects as created for BT-540-LotsGroup, BT-541-LotsGroup, BT-5421-LotsGroup, BT-5422-LotsGroup, BT-5423-LotsGroup and BT-734-LotsGroup.

<a href="operations.md#get-the-lot-group-for-a-procurementprojectlot">Get the lot group for the ProcurementProjectLot</a>.
For each `cac:SubordinateAwardingCriterion`, add or update a corresponding `AwardCriterion` in the lot group's `.awardCriteria.criteria` array and map to the award critereon's `.type`.

```xml
<cac:SubordinateAwardingCriterion>
  <cbc:AwardingCriterionTypeCode listName="award-criterion-type">quality</cbc:AwardingCriterionTypeCode>
</cac:SubordinateAwardingCriterion>
```

```json
{
  "tender": {
    "lotGroups": [
      {
        "awardCriteria": {
          "criteria": [
            {
              "type": "quality"
            }
          ]
        }
      }
    ]
  }
}
```

</td>
      </tr>
      <tr id="BT-54-Lot">
        <td class="field break-all">
            <p><b>BT-54-Lot</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/procedure-lot-part-information.html#extensionsSection"></a><br>Options Description</p><p><i>BT-54:</i> The description of the options.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='Lot']/cac:ProcurementProject/cac:ContractExtension/cbc:OptionsDescription</span></code>
        </td>
        <td class="mapping">

<a href="operations.md#get-the-lot-for-a-procurementprojectlot">Get the lot for the ProcurementProjectLot</a> and map to its `.options.description`.

```xml
<cac:ContractExtension>
  <cbc:OptionsDescription languageID="ENG">The buyer reserves the right to ...</cbc:OptionsDescription>
</cac:ContractExtension>
```

```json
{
  "tender": {
    "lots": [
      {
        "options": {
          "description": "The buyer reserves the right to..."
        }
      }
    ]
  }
}
```

</td>
      </tr>
      <tr id="BT-540-Lot">
        <td class="field break-all">
            <p><b>BT-540-Lot</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/procedure-lot-part-information.html#awardCriteriaSection"></a><br>Award Criterion Description</p><p><i>BT-540:</i> The description of the award criterion.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='Lot']/cac:TenderingTerms/cac:AwardingTerms/cac:AwardingCriterion/cac:SubordinateAwardingCriterion/cbc:Description</span></code>
        </td>
        <td class="mapping">

This field maps to the same `AwardCriterion` objects as created for BT-539-Lot, BT-541-Lot, BT-5421-Lot, BT-5422-Lot, BT-5423-Lot and BT-734-Lot.

<a href="operations.md#get-the-lot-for-a-procurementprojectlot">Get the lot for the ProcurementProjectLot</a>.
For each `cac:SubordinateAwardingCriterion`, add or update a corresponding `AwardCriterion` in the lot's `.awardCriteria.criteria` array and map to the award criterion's `.description`.

```xml
<cac:SubordinateAwardingCriterion>
  <cbc:Description languageID="ENG">Tenders with a quality score less than 65...</cbc:Description>
</cac:SubordinateAwardingCriterion>
```

```json
{
  "tender": {
    "lots": [
      {
        "awardCriteria": {
          "criteria": [
            {
              "description": "Tenders with a quality score less than 65..."
            }
          ]
        }
      }
    ]
  }
}
```

</td>
      </tr>
      <tr id="BT-540-LotsGroup">
        <td class="field break-all">
            <p><b>BT-540-LotsGroup</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/procedure-lot-part-information.html#awardCriteriaSection"></a><br>Award Criterion Description</p><p><i>BT-540:</i> The description of the award criterion.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='LotsGroup']/cac:TenderingTerms/cac:AwardingTerms/cac:AwardingCriterion/cac:SubordinateAwardingCriterion/cbc:Description</span></code>
        </td>
        <td class="mapping">

This field maps to the same `AwardCriterion` objects as created for BT-539-LotsGroup, BT-541-LotsGroup, BT-5421-LotsGroup, BT-5422-LotsGroup, BT-5423-LotsGroup and BT-734-LotsGroup.

<a href="operations.md#get-the-lot-group-for-a-procurementprojectlot">Get the lot group for the ProcurementProjectLot</a>.
For each `cac:SubordinateAwardingCriterion`, add or update a corresponding `AwardCriterion` in the lot group's `.awardCriteria.criteria` array and map to the award criterion's `.description`.

```xml
<cac:SubordinateAwardingCriterion>
  <cbc:Description languageID="ENG">Tenders with a quality score less than 65...</cbc:Description>
</cac:SubordinateAwardingCriterion>
```

```json
{
  "tender": {
    "lotGroups": [
      {
        "awardCriteria": {
          "criteria": [
            {
              "description": "Tenders with a quality score less than 65..."
            }
          ]
        }
      }
    ]
  }
}
```

</td>
      </tr>
      <tr id="BT-541-Lot">
        <td class="field break-all">
            <p><b>BT-541-Lot</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/procedure-lot-part-information.html#awardCriteriaSection"></a><br>Award Criterion Number</p><p><i>BT-541:</i> A number linked to an award criterion.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='Lot']/cac:TenderingTerms/cac:AwardingTerms/cac:AwardingCriterion/cac:SubordinateAwardingCriterion/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:AwardCriterionParameter/efbc:ParameterNumeric</span></code>
        </td>
        <td class="mapping">

This field maps to the same `AwardCriterion` objects as created for BT-539-Lot, BT-540-Lot, BT-5421-Lot, BT-5422-Lot, BT-5423-Lot and BT-734-Lot and to the same `AwardCriterionNumber` objects as created for BT-5421-Lot, BT-5422-Lot and BT-5423-Lot.

<a href="operations.md#get-the-lot-for-a-procurementprojectlot">Get the lot for the ProcurementProjectLot</a>.
For each `cac:SubordinateAwardingCriterion`, add or update a corresponding `AwardCriterion` in the lot's `.awardCriteria.criteria` array.
For each `efac:AwardCriterionParameter`, add or update a corresponding `AwardCriterionNumber` in the award criterion's `.numbers` array and map to the award criteron number's `.number`.

```xml
<efac:AwardCriterionParameter>
  <efbc:ParameterNumeric>50</efbc:ParameterNumeric>
</efac:AwardCriterionParameter>
```

```json
{
  "tender": {
    "lots": [
      {
        "awardCriteria": {
          "criteria": [
            {
              "numbers": [
                {
                  "number": 50
                }
              ]
            }
          ]
        }
      }
    ]
  }
}
```

</td>
      </tr>
      <tr id="BT-541-LotsGroup">
        <td class="field break-all">
            <p><b>BT-541-LotsGroup</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/procedure-lot-part-information.html#awardCriteriaSection"></a><br>Award Criterion Number</p><p><i>BT-541:</i> A number linked to an award criterion.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='LotsGroup']/cac:TenderingTerms/cac:AwardingTerms/cac:AwardingCriterion/cac:SubordinateAwardingCriterion/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:AwardCriterionParameter/efbc:ParameterNumeric</span></code>
        </td>
        <td class="mapping">

This field maps to the same `AwardCriterion` objects as created for BT-539-LotsGroup, BT-540-LotsGroup, BT-541-LotsGroup, BT-5421-LotsGroup, BT-5422-LotsGroup, BT-5423-LotsGroup and BT-734-LotsGroup and to the same `AwardCriterionNumber` objects as created for BT-5421-LotsGroup, BT-5422-LotsGroup and BT-5423-LotsGroup.

<a href="operations.md#get-the-lot-group-for-a-procurementprojectlot">Get the lot group for the ProcurementProjectLot</a>.
For each `cac:SubordinateAwardingCriterion`, add or update a corresponding `AwardCriterion` in the lot group's `.awardCriteria.criteria` array.
For each `efac:AwardCriterionParameter`, add or update a corresponding `AwardCriterionNumber` in the award criterion's `.numbers` array and map to the award criteron number's `.number`.

```xml
<efac:AwardCriterionParameter>
  <efbc:ParameterNumeric>50</efbc:ParameterNumeric>
</efac:AwardCriterionParameter>
```

```json
{
  "tender": {
    "lotGroups": [
      {
        "awardCriteria": {
          "criteria": [
            {
              "numbers": [
                {
                  "number": 50
                }
              ]
            }
          ]
        }
      }
    ]
  }
}
```

</td>
      </tr>
      <tr id="BT-5421-Lot">
        <td class="field break-all">
            <p><b>BT-5421-Lot</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/procedure-lot-part-information.html#awardCriteriaSection"></a><br>Award Criterion Number Weight</p><p><i>BT-5421:</i> Whether the number linked to an award criterion is a type of weight (e.g. a percentage).</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='Lot']/cac:TenderingTerms/cac:AwardingTerms/cac:AwardingCriterion/cac:SubordinateAwardingCriterion/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:AwardCriterionParameter/efbc:ParameterCode[@listName='number-weight']</span></code>
        </td>
        <td class="mapping">

This field maps to the same `AwardCriterion` objects as created for BT-539-Lot, BT-540-Lot, BT-541-Lot, BT-5422-Lot, BT-5423-Lot and BT-734-Lot and to the same `AwardCriterionNumber` objects as created for BT-541-Lot, BT-5422-Lot and BT-5423-Lot.

<a href="operations.md#get-the-lot-for-a-procurementprojectlot">Get the lot for the ProcurementProjectLot</a>.
For each `cac:SubordinateAwardingCriterion`, add or update a corresponding `AwardCriterion` in the lot's `.awardCriteria.criteria` array.
For each `efac:AwardCriterionParameter`, add or update a corresponding `AwardCriterionNumber` in the award criterion's `.numbers` array and map the code to the award criterion number's `.weight` according to the <a href="codelists/number-weight">number weight mapping table</a>.

```xml
<efac:AwardCriterionParameter>
  <efbc:ParameterCode listName="number-weight">per-exa</efbc:ParameterCode>
</efac:AwardCriterionParameter>
```

```json
{
  "tender": {
    "lots": [
      {
        "awardCriteria": {
          "criteria": [
            {
              "numbers": [
                {
                  "weight": "percentageExact"
                }
              ]
            }
          ]
        }
      }
    ]
  }
}
```

</td>
      </tr>
      <tr id="BT-5421-LotsGroup">
        <td class="field break-all">
            <p><b>BT-5421-LotsGroup</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/procedure-lot-part-information.html#awardCriteriaSection"></a><br>Award Criterion Number Weight</p><p><i>BT-5421:</i> Whether the number linked to an award criterion is a type of weight (e.g. a percentage).</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='LotsGroup']/cac:TenderingTerms/cac:AwardingTerms/cac:AwardingCriterion/cac:SubordinateAwardingCriterion/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:AwardCriterionParameter/efbc:ParameterCode[@listName='number-weight']</span></code>
        </td>
        <td class="mapping">

This field maps to the same `AwardCriterion` objects as created for BT-539-LotsGroup, BT-540-LotsGroup, BT-541-LotsGroup, BT-5422-LotsGroup, BT-5423-LotsGroup and BT-734-LotsGroup and to the same `AwardCriterionNumber` objects as created for BT-541-LotsGroup, BT-5422-LotsGroup and BT-5423-LotsGroup.

<a href="operations.md#get-the-lot-group-for-a-procurementprojectlot">Get the lot group for the ProcurementProjectLot</a>.
For each `cac:SubordinateAwardingCriterion`, add or update a corresponding `AwardCriterion` in the lot group's `.awardCriteria.criteria` array.
For each `efac:AwardCriterionParameter`, add or update a corresponding `AwardCriterionNumber` in the award criterion's `.numbers` array and map the code to the award criterion number's `.weight` according to the <a href="codelists/number-weight">number weight mapping table</a>.

```xml
<efac:AwardCriterionParameter>
  <efbc:ParameterCode listName="number-weight">per-exa</efbc:ParameterCode>
</efac:AwardCriterionParameter>
```

```json
{
  "tender": {
    "lotGroups": [
      {
        "awardCriteria": {
          "criteria": [
            {
              "numbers": [
                {
                  "weight": "percentageExact"
                }
              ]
            }
          ]
        }
      }
    ]
  }
}
```

</td>
      </tr>
      <tr id="BT-5422-Lot">
        <td class="field break-all">
            <p><b>BT-5422-Lot</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/procedure-lot-part-information.html#awardCriteriaSection"></a><br>Award Criterion Number Fixed</p><p><i>BT-5422:</i> Whether the number linked to an award criterion is a fixed value (e.g. a fixed price, a fixed cost).</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='Lot']/cac:TenderingTerms/cac:AwardingTerms/cac:AwardingCriterion/cac:SubordinateAwardingCriterion/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:AwardCriterionParameter/efbc:ParameterCode[@listName='number-fixed']</span></code>
        </td>
        <td class="mapping">

This field maps to the same `AwardCriterion` objects as created for BT-539-Lot, BT-540-Lot, BT-541-Lot, BT-5421-Lot, BT-5423-Lot and BT-734-Lot and to the same `AwardCriterionNumber` objects as created for BT-541-Lot, BT-5421-Lot and BT-5423-Lot.

<a href="operations.md#get-the-lot-for-a-procurementprojectlot">Get the lot for the ProcurementProjectLot</a>.
For each `cac:SubordinateAwardingCriterion`, add or update a corresponding `AwardCriterion` in the lot's `.awardCriteria.criteria` array.
For each `efac:AwardCriterionParameter`, add or update a corresponding `AwardCriterionNumber` in the award criterion's `.numbers` array and map the code to the award criterion number's `.fixed` according to the <a href="codelists/number-fixed">number fixed mapping table</a>.

```xml
<efac:AwardCriterionParameter>
  <efbc:ParameterCode listName="number-fixed">fix-tot</efbc:ParameterCode>
</efac:AwardCriterionParameter>
```

```json
{
  "tender": {
    "lots": [
      {
        "awardCriteria": {
          "criteria": [
            {
              "numbers": [
                {
                  "fixed": "total"
                }
              ]
            }
          ]
        }
      }
    ]
  }
}
```

</td>
      </tr>
      <tr id="BT-5422-LotsGroup">
        <td class="field break-all">
            <p><b>BT-5422-LotsGroup</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/procedure-lot-part-information.html#awardCriteriaSection"></a><br>Award Criterion Number Fixed</p><p><i>BT-5422:</i> Whether the number linked to an award criterion is a fixed value (e.g. a fixed price, a fixed cost).</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='LotsGroup']/cac:TenderingTerms/cac:AwardingTerms/cac:AwardingCriterion/cac:SubordinateAwardingCriterion/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:AwardCriterionParameter/efbc:ParameterCode[@listName='number-fixed']</span></code>
        </td>
        <td class="mapping">

This field maps to the same `AwardCriterion` objects as created for BT-539-LotsGroup, BT-540-LotsGroup, BT-541-LotsGroup, BT-5421-LotsGroup, BT-5423-LotsGroup and BT-734-LotsGroup and to the same `AwardCriterionNumber` objects as created for BT-541-LotsGroup, BT-5421-LotsGroup and BT-5423-LotsGroup.

<a href="operations.md#get-the-lot-group-for-a-procurementprojectlot">Get the lot group for the ProcurementProjectLot</a>.
For each `cac:SubordinateAwardingCriterion`, add or update a corresponding `AwardCriterion` in the lot group's `.awardCriteria.criteria` array.
For each `efac:AwardCriterionParameter`, add or update a corresponding `AwardCriterionNumber` in the award criterion's `.numbers` array and map the code to the award criterion number's `.fixed` according to the <a href="codelists/number-fixed">number fixed mapping table</a>.

```xml
<efac:AwardCriterionParameter>
  <efbc:ParameterCode listName="number-fixed">fix-tot</efbc:ParameterCode>
</efac:AwardCriterionParameter>
```

```json
{
  "tender": {
    "lotGroups": [
      {
        "awardCriteria": {
          "criteria": [
            {
              "numbers": [
                {
                  "fixed": "total"
                }
              ]
            }
          ]
        }
      }
    ]
  }
}
```

</td>
      </tr>
      <tr id="BT-5423-Lot">
        <td class="field break-all">
            <p><b>BT-5423-Lot</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/procedure-lot-part-information.html#awardCriteriaSection"></a><br>Award Criterion Number Threshold</p><p><i>BT-5423:</i> Whether the number linked to an award criterion is a type of threshold (e.g. a minimum score, a maximum number of tenders with the highest score passing).</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='Lot']/cac:TenderingTerms/cac:AwardingTerms/cac:AwardingCriterion/cac:SubordinateAwardingCriterion/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:AwardCriterionParameter/efbc:ParameterCode[@listName='number-threshold']</span></code>
        </td>
        <td class="mapping">

This field maps to the same `AwardCriterion` objects as created for BT-539-Lot, BT-540-Lot, BT-541-Lot, BT-5421-Lot, BT-5422-Lotand BT-734-Lot and to the same `AwardCriterionNumber` objects as created for BT-541-Lot, BT-5421-Lot and BT-5422-Lot.

<a href="operations.md#get-the-lot-for-a-procurementprojectlot">Get the lot for the ProcurementProjectLot</a>.

For each `cac:SubordinateAwardingCriterion`, add or update a corresponding `AwardCriterion` in the lot's `.awardCriteria.criteria` array.

For each `efac:AwardCriterionParameter`, add or update a corresponding `AwardCriterionNumber` in the award criterion's `.numbers` array and map the code to the award criterion number's `.threshold` according to the <a href="codelists/number-threshold">number threshold mapping table</a>.

```xml
<efac:AwardCriterionParameter>
  <efbc:ParameterCode listName="number-threshold">max-pass</efbc:ParameterCode>
</efac:AwardCriterionParameter>
```

```json
{
  "tender": {
    "lots": [
      {
        "awardCriteria": {
          "criteria": [
            {
              "numbers": [
                {
                  "threshold": "maximumBids"
                }
              ]
            }
          ]
        }
      }
    ]
  }
}
```

</td>
      </tr>
      <tr id="BT-5423-LotsGroup">
        <td class="field break-all">
            <p><b>BT-5423-LotsGroup</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/procedure-lot-part-information.html#awardCriteriaSection"></a><br>Award Criterion Number Threshold</p><p><i>BT-5423:</i> Whether the number linked to an award criterion is a type of threshold (e.g. a minimum score, a maximum number of tenders with the highest score passing).</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='LotsGroup']/cac:TenderingTerms/cac:AwardingTerms/cac:AwardingCriterion/cac:SubordinateAwardingCriterion/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:AwardCriterionParameter/efbc:ParameterCode[@listName='number-threshold']</span></code>
        </td>
        <td class="mapping">

This field maps to the same `AwardCriterion` objects as created for BT-539-LotsGroup, BT-540-LotsGroup, BT-541-LotsGroup, BT-5421-LotsGroup, BT-5422-LotsGroup and BT-734-LotsGroup and to the same `AwardCriterionNumber` objects as created for BT-541-LotsGroup, BT-5421-LotsGroup and BT-5422-LotsGroup.

<a href="operations.md#get-the-lot-group-for-a-procurementprojectlot">Get the lot group for the ProcurementProjectLot</a>.
For each `cac:SubordinateAwardingCriterion`, add or update a corresponding `AwardCriterion` in the lot group's `.awardCriteria.criteria` array.
For each `efac:AwardCriterionParameter`, add or update a corresponding `AwardCriterionNumber` in the award criterion's `.numbers` array and map the code to the award criterion number's `.threshold` according to the <a href="codelists/number-threshold">number threshold mapping table</a>.

```xml
<efac:AwardCriterionParameter>
  <efbc:ParameterCode listName="number-threshold">max-pass</efbc:ParameterCode>
</efac:AwardCriterionParameter>
```

```json
{
  "tender": {
    "lotGroups": [
      {
        "awardCriteria": {
          "criteria": [
            {
              "numbers": [
                {
                  "threshold": "maximumBids"
                }
              ]
            }
          ]
        }
      }
    ]
  }
}
```

</td>
      </tr>
      <tr id="BT-543-Lot">
        <td class="field break-all">
            <p><b>BT-543-Lot</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/procedure-lot-part-information.html#awardCriteriaSection"></a><br>Award Criteria Complicated</p><p><i>BT-543:</i> The mathematical equation or any other description used for complicated weighing of criteria (e.g. non-linear weighing, the analytic hierarchy process) when a weighing cannot be expressed per criterion. </p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='Lot']/cac:TenderingTerms/cac:AwardingTerms/cac:AwardingCriterion/cbc:CalculationExpression</span></code>
        </td>
        <td class="mapping">

<a href="operations.md#get-the-lot-for-a-procurementprojectlot">Get the lot for the ProcurementProjectLot</a> and map to its `.awardCriteria.weightingDescription`.

```xml
<cac:AwardingCriterion>
  <cbc:CalculationExpression languageID="ENG">Price-quality score calculation is based on &#8230;</cbc:CalculationExpression>
</cac:AwardingCriterion>
```

```json
{
  "tender": {
    "lots": [
      {
        "awardCriteria": {
          "weightingDescription": "Price-quality score calculation is based on …"
        }
      }
    ]
  }
}
```

</td>
      </tr>
      <tr id="BT-543-LotsGroup">
        <td class="field break-all">
            <p><b>BT-543-LotsGroup</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/procedure-lot-part-information.html#awardCriteriaSection"></a><br>Award Criteria Complicated</p><p><i>BT-543:</i> The mathematical equation or any other description used for complicated weighing of criteria (e.g. non-linear weighing, the analytic hierarchy process) when a weighing cannot be expressed per criterion. </p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='LotsGroup']/cac:TenderingTerms/cac:AwardingTerms/cac:AwardingCriterion/cbc:CalculationExpression</span></code>
        </td>
        <td class="mapping">

<a href="operations.md#get-the-lot-group-for-a-procurementprojectlot">Get the lot group for the ProcurementProjectLot</a> and map to its `.awardCriteria.weightingDescription`.

```xml
<cac:AwardingCriterion>
  <cbc:CalculationExpression languageID="ENG">Price-quality score calculation is based on &#8230;</cbc:CalculationExpression>
</cac:AwardingCriterion>
```

```json
{
  "tender": {
    "lotGroups": [
      {
        "awardCriteria": {
          "weightingDescription": "Price-quality score calculation is based on …"
        }
      }
    ]
  }
}
```

</td>
      </tr>
      <tr id="BT-553-Tender">
        <td class="field break-all">
            <p><b>BT-553-Tender</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/competition-results.html#lotTenderSection"></a><br>Subcontracting Value</p><p><i>BT-553:</i> The estimated value of the part of the contract that the contractor will subcontract to third parties.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:NoticeResult/efac:LotTender/efac:SubcontractingTerm/efbc:TermAmount</span></code>
        </td>
        <td class="mapping">

<a href="operations.md#get-the-bid-for-a-lottender">Get the bid for the LotTender</a> and map to its `.subcontracting.value.amount`.  Map `@currencyID` to the value's `.currency`.

```xml
<efac:SubcontractingTerm>
  <efbc:TermAmount currencyID="EUR">9999999.99</efbc:TermAmount>
</efac:SubcontractingTerm>
```

```json
{
  "bids": {
    "details": [
      {
        "subcontracting": {
          "value": {
            "amount": 9999999.99,
            "currency": "EUR"
          }
        }
      }
    ]
  }
}
```

</td>
      </tr>
      <tr id="BT-554-Tender">
        <td class="field break-all">
            <p><b>BT-554-Tender</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/competition-results.html#lotTenderSection"></a><br>Subcontracting Description</p><p><i>BT-554:</i> The description of the part of the contract that the contractor will subcontract to third parties.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:NoticeResult/efac:LotTender/efac:SubcontractingTerm/efbc:TermDescription</span></code>
        </td>
        <td class="mapping">

<a href="operations.md#get-the-bid-for-a-lottender">Get the bid for the LotTender</a> and map to its `.subcontracting.description`.

```xml
<efac:SubcontractingTerm>
  <efbc:TermDescription languageID="ENG">The subcontracting will be...</efbc:TermDescription>
</efac:SubcontractingTerm>
```

```json
{
  "bids": {
    "details": [
      {
        "subcontracting": {
          "description": "The subcontracting will be..."
        }
      }
    ]
  }
}
```

</td>
      </tr>
      <tr id="BT-555-Tender">
        <td class="field break-all">
            <p><b>BT-555-Tender</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/competition-results.html#lotTenderSection"></a><br>Subcontracting Percentage</p><p><i>BT-555:</i> The estimated percentage of the contract that the contractor will subcontract to third parties compared to the whole contract.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:NoticeResult/efac:LotTender/efac:SubcontractingTerm/efbc:TermPercent</span></code>
        </td>
        <td class="mapping">

<a href="operations.md#get-the-bid-for-a-lottender">Get the bid for the LotTender</a>, divide number by 100 and map to the bid's `.subcontracting.minimumPercentage` and `.subcontracting.maximumPercentage`.

```xml
<efac:SubcontractingTerm>
  <efbc:TermPercent>30</efbc:TermPercent>
</efac:SubcontractingTerm>
```

```json
{
  "bids": {
    "details": [
      {
        "subcontracting": {
          "minimumPercentage": 0.3,
          "maximumPercentage": 0.3
        }
      }
    ]
  }
}
```

</td>
      </tr>
      <tr id="BT-556-NoticeResult">
        <td class="field break-all">
            <p><b>BT-556-NoticeResult</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/competition-results.html#_notice_aggregated_amounts"></a><br>Group Framework Value Lot Identifier</p><p><i>BT-556:</i> An identifier of a lot within the procedure that is part of a group of lots whose maximum value is lower than the sum of maximum values of individual lots (e.g. when the same budget is shared for several lots). These are maximum values as calculated on the basis of the winner’s tender or winners’ tenders.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:NoticeResult/efac:GroupFramework/efac:TenderLot/cbc:ID</span></code>
        </td>
        <td class="mapping">

Discard.

```xml
<efac:TenderLot>
  <cbc:ID schemeName="LotsGroup">GLO-0001</cbc:ID>
</efac:TenderLot>
```



</td>
      </tr>
      <tr id="BT-57-Lot">
        <td class="field break-all">
            <p><b>BT-57-Lot</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/procedure-lot-part-information.html#extensionsSection"></a><br>Renewal Description</p><p><i>BT-57:</i> Any other information about the renewal(s).</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='Lot']/cac:ProcurementProject/cac:ContractExtension/cac:Renewal/cac:Period/cbc:Description</span></code>
        </td>
        <td class="mapping">

<a href="operations.md#get-the-lot-for-a-procurementprojectlot">Get the lot for the ProcurementProjectLot</a> and map to its `.renewal.description`.

```xml
<cac:Period>
  <cbc:Description languageID="ENG">The buyer reserves the right to ...</cbc:Description>
</cac:Period>
```

```json
{
  "tender": {
    "lots": [
      {
        "renewal": {
          "description": "The buyer reserves the right to ..."
        }
      }
    ]
  }
}
```

</td>
      </tr>
      <tr id="BT-578-Lot">
        <td class="field break-all">
            <p><b>BT-578-Lot</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/procedure-lot-part-information.html#securityClearanceSection"></a><br>Security Clearance</p><p><i>BT-578:</i> A security clearance is required.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='Lot']/cac:TenderingTerms/cac:SecurityClearanceTerm/cbc:Code</span></code>
        </td>
        <td class="mapping">

Discard. If `.otherRequirements.securityClearance` is set, a security clearance is required.

```xml
<cac:SecurityClearanceTerm>
  <cbc:Code listName="required">true</cbc:Code>
</cac:SecurityClearanceTerm>
```



</td>
      </tr>
      <tr id="BT-58-Lot">
        <td class="field break-all">
            <p><b>BT-58-Lot</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/procedure-lot-part-information.html#extensionsSection"></a><br>Renewal Maximum</p><p><i>BT-58:</i> The maximum number of times the contract can be renewed. By renewing, the buyer reserves the right (i.e. not an obligation) to renew the contract (i.e. extend its duration) without a new procurement procedure. For example, a contract may be valid for one year and the buyer may keep a possibility to renew it (e.g. once, twice) for another three months, if he is content with the services he received.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='Lot']/cac:ProcurementProject/cac:ContractExtension/cbc:MaximumNumberNumeric</span></code>
        </td>
        <td class="mapping">

<a href="operations.md#get-the-lot-for-a-procurementprojectlot">Get the lot for the ProcurementProjectLot</a> and map to its `.renewal.maximumRenewals`.

```xml
<cac:ContractExtension>
  <cbc:MaximumNumberNumeric>3</cbc:MaximumNumberNumeric>
</cac:ContractExtension>
```

```json
{
  "tender": {
    "lots": [
      {
        "renewal": {
          "maximumRenewals": 3
        }
      }
    ]
  }
}
```

</td>
      </tr>
      <tr id="BT-60-Lot">
        <td class="field break-all">
            <p><b>BT-60-Lot</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/procedure-lot-part-information.html#EUFundsSection"></a><br>EU Funds</p><p><i>BT-60:</i> The procurement is at least partially financed by Union funds such as the European Structural and Investment Funds or grants awarded by the Union.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='Lot']/cac:TenderingTerms/cbc:FundingProgramCode[@listName='eu-funded']</span></code>
        </td>
        <td class="mapping">

Get the `Organization` object whose `.name` is 'European Union'. If none exists yet:

- <a href="operations.md#add-a-party">Add a party</a>.
- Set its `.name` to 'European Union'.
- Add 'funder' to its `.roles`.

```xml
<efac:Funding>
  <cbc:FundingProgramCode listName="eu-funded">eu-funds</cbc:FundingProgramCode>
</efac:Funding>
```

```json
{
  "parties": [
    {
      "name": "European Union",
      "roles": [
        "funder"
      ]
    }
  ]
}
```

</td>
      </tr>
      <tr id="BT-610-Procedure-Buyer">
        <td class="field break-all">
            <p><b>BT-610-Procedure-Buyer</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/parties.html#_buyer_information"></a><br>Activity Entity</p><p><i>BT-610:</i> The main activity of the contracting entity.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ContractingParty/cac:ContractingActivity/cbc:ActivityTypeCode[@listName='entity-activity']</span></code>
        </td>
        <td class="mapping">

<a href="operations.md#get-the-organization-for-the-buyer">Get the organization for the buyer</a> and add a `Classification` object to its `.details.classifications` array.

- Map to the classification's `.id`.
- Look up the code's label in the <a href="https://op.europa.eu/en/web/eu-vocabularies/concept-scheme/-/resource?uri=http://publications.europa.eu/resource/authority/main-activity">authority table</a> and map it to `.description`.
- If the code's definition in the authority table includes <a href="https://ec.europa.eu/eurostat/statistics-explained/index.php?title=Glossary:Classification_of_the_functions_of_government_(COFOG)">"COFOG"</a>, set the classification's `.scheme` to 'COFOG'. Otherwise, set it to "Directive 2014/25/EU".

```xml
<cac:ContractingActivity>
  <cbc:ActivityTypeCode listName="entity-activity">gas-oil</cbc:ActivityTypeCode>
</cac:ContractingActivity>
```

```json
{
  "parties": [
    {
      "id": "ORG-0001",
      "details": {
        "classifications": [
          {
            "scheme": "Directive 2014/25/EU",
            "id": "gas-oil",
            "description": "Activities related to the exploitation of a geographical area for the purpose of extracting oil or gas."
          }
        ]
      }
    }
  ]
}
```

</td>
      </tr>
      <tr id="BT-6110-Contract">
        <td class="field break-all">
            <p><b>BT-6110-Contract</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/competition-results.html#settledContractSection"></a><br>Contract EU Funds Details</p><p><i>BT-6110:</i> Further information about the Union programme or project used at least partially finance the procurement.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:NoticeResult/efac:SettledContract/efac:Funding/cbc:Description</span></code>
        </td>
        <td class="mapping">

This field maps to the same `finance` objects as created for BT-5011-Contract and BT-722-Contract.
<a href="operations.md#get-the-contract-for-a-settledcontract">Get the contract for the SettledContract</a>.
For each `efac:Funding`, add or update the corresponding `Finance` object in the contract's `.finance` array and map to its `.description`.

```xml
<efac:Funding>
  <cbc:FundingProgram>Program for the development ...</cbc:FundingProgram>
</efac:Funding>
```

```json
{
  "contracts": [
    {
      "finance": [
        {
          "description": "Program for the development ..."
        }
      ]
    }
  ]
}
```

</td>
      </tr>
      <tr id="BT-6140-Lot">
        <td class="field break-all">
            <p><b>BT-6140-Lot</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/procedure-lot-part-information.html#EUFundsSection"></a><br>EU Funds Details</p><p><i>BT-6140:</i> Further information about the Union programme or project used at least partially finance the procurement.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='Lot']/cac:TenderingTerms/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:Funding/cbc:Description</span></code>
        </td>
        <td class="mapping">

This field maps to the same `finance` objects as created for BT-5010-Lot and BT-7220-Lot.
If BT-5010-Lot is not present follow the guidance for BT-5010-Lot, setting the `.id` of the `Finance` object incrementally based on its position in the `finance` array rather than the value of BT-5010-Lot.
For each `efac:Funding`, add or update the corresponding `Finance` object in the budget's `.finance` array and map to its `.description`.

```xml
<efac:Funding>
  <cbc:Description languageID="ENG">This project will be financed ...</cbc:Description>
</efac:Funding>
```

```json
{
  "planning": {
    "budget": {
      "finance": [
        {
          "description": "This project will be financed ..."
        }
      ]
    }
  }
}
```

</td>
      </tr>
      <tr id="BT-615-Lot">
        <td class="field break-all">
            <p><b>BT-615-Lot</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/procedure-lot-part-information.html#procurementDocsSection"></a><br>Documents Restricted URL</p><p><i>BT-615:</i> The internet address with information on accessing the restricted (part of the) procurement documents.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='Lot']/cac:TenderingTerms/cac:CallForTendersDocumentReference[cbc:DocumentType/text()='restricted-document']/cac:Attachment/cac:ExternalReference/cbc:URI</span></code>
        </td>
        <td class="mapping">

This field maps to the same `ParticipationFee` objects as created for BT-14-Lot and BT-707-Lot.

<a href="operations.md#get-the-lot-for-a-procurementprojectlot">Get the lot for the ProcurementProjectLot</a>.

For each `cac:CallForTendersDocumentReference`, add or update the corresponding `ParticipationFee` object in the lot's `participationFees` array and map to its `.description`. If the document type label has already been mapped to this field append to it with ' - ' (space, dash, space).

```xml
<cac:ExternalReference>
  <cbc:URI>https://mywebsite.com/proc/2019024/accessinfo</cbc:URI>
</cac:ExternalReference>
```

```json
{
  "tender": {
    "lots": [
      {
        "participationFees": [
          {
            "description": "https://mywebsite.com/proc/2019024/accessinfo"
          }
        ]
      }
    ]
  }
}
```

</td>
      </tr>
      <tr id="BT-615-Part">
        <td class="field break-all">
            <p><b>BT-615-Part</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/procedure-lot-part-information.html#procurementDocsSection"></a><br>Documents Restricted URL</p><p><i>BT-615:</i> The internet address with information on accessing the restricted (part of the) procurement documents.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='Part']/cac:TenderingTerms/cac:CallForTendersDocumentReference[cbc:DocumentType/text()='restricted-document']/cac:Attachment/cac:ExternalReference/cbc:URI</span></code>
        </td>
        <td class="mapping">

This field maps to the same objects as created for BT-14-Part and BT-707-Part.
For each `cac:CallForTendersDocumentReference`, add or update the corresponding `ParticipationFee` object in the `participationFees` array and map to its `.description`.

```xml
<cac:ExternalReference>
  <cbc:URI>https://mywebsite.com/proc/2019024/accessinfo</cbc:URI>
</cac:ExternalReference>
```

```json
{
  "tender": {
    "participationFees": [
      {
        "description": "https://mywebsite.com/proc/2019024/accessinfo"
      }
    ]
  }
}
```

</td>
      </tr>
      <tr id="BT-625-Lot">
        <td class="field break-all">
            <p><b>BT-625-Lot</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/procedure-lot-part-information.html#quantitySection"></a><br>Unit</p><p><i>BT-625:</i> The unit which the good, service, or work comes in, for example hours or kilograms. Where the CPV code is a supply which does not need a further unit (e.g. cars), then no unit needs to be given and quantity is taken to be an amount, e.g. the "number of cars". </p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='Lot']/cac:ProcurementProject/cbc:EstimatedOverallContractQuantity/@unitCode</span></code>
        </td>
        <td class="mapping">

- <a href="operations.md#get-the-item-for-a-procurementprojectlot">Get the item for the ProcurementProjectLot</a> and map to its `.unit.id`.
- Set the item's `.unit.scheme` to <a href="https://op.europa.eu/en/web/eu-vocabularies/concept-scheme/-/resource?uri=http://publications.europa.eu/resource/authority/measurement-unit">'EU Measurement unit'</a>.
- Look up the code's label in the <a href="https://op.europa.eu/en/web/eu-vocabularies/concept-scheme/-/resource?uri=http://publications.europa.eu/resource/authority/measurement-unit">authority table</a> and map it to `.unit.name`.

```xml
<cbc:EstimatedOverallContractQuantity unitCode="TNE">45000</cbc:EstimatedOverallContractQuantity>
```

```json
{
  "tender": {
    "items": [
      {
        "unit": {
          "scheme": "EU Measurement unit",
          "name": "tonne"
        }
      }
    ]
  }
}
```

</td>
      </tr>
      <tr id="BT-63-Lot">
        <td class="field break-all">
            <p><b>BT-63-Lot</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/procedure-lot-part-information.html#variantsSection"></a><br>Variants</p><p><i>BT-63:</i> Whether tenderers are required, allowed, or not allowed to submit tenders which fulfil the buyer's needs differently than as proposed in the procurement documents. Further conditions for submitting variant tenders are in the procurement documents.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='Lot']/cac:TenderingTerms/cbc:VariantConstraintCode</span></code>
        </td>
        <td class="mapping">

<a href="operations.md#get-the-lot-for-a-procurementprojectlot">Get the lot for the ProcurementProjectLot</a> and set its `.submissionTerms.variantPolicy` according to <a href="https://extensions.open-contracting.org/en/extensions/submissionTerms/master/codelists/">the allowed values</a>.

```xml
<cac:TenderingTerms>
  <cbc:VariantConstraintCode listName="permission">allowed</cbc:VariantConstraintCode>
</cac:TenderingTerms>
```

```json
{
  "tender": {
    "lots": [
      {
        "submissionTerms": {
          "variantPolicy": "allowed"
        }
      }
    ]
  }
}
```

</td>
      </tr>
      <tr id="BT-630(d)-Lot">
        <td class="field break-all">
            <p><b>BT-630(d)-Lot</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/procedure-lot-part-information.html#expressionsDeadlineSection"></a><br>Deadline Receipt Expressions</p><p><i>BT-630:</i> The time limit for receipt of expressions of interest.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='Lot']/cac:TenderingProcess/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:InterestExpressionReceptionPeriod/cbc:EndDate</span></code>
        </td>
        <td class="mapping">

<a href="operations.md#get-the-lot-for-a-procurementprojectlot">Get the lot for the ProcurementProjectLot</a>, combine with <a href="#BT-630(t)-lot">BT-630(t)-Lot</a>, <a href="operations.md#convert-a-date-to-iso-format">convert date to ISO format</a> and map to the lot's `tenderPeriod.endDate`.

```xml
<efac:InterestExpressionReceptionPeriod>
  <cbc:EndDate>2019-10-28+01:00</cbc:EndDate>
</efac:InterestExpressionReceptionPeriod>
```

```json
{
  "tender": {
    "lots": [
      {
        "tenderPeriod": {
          "endDate": "2019-10-28T23:59:59+01:00"
        }
      }
    ]
  }
}
```

</td>
      </tr>
      <tr id="BT-630(t)-Lot">
        <td class="field break-all">
            <p><b>BT-630(t)-Lot</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/procedure-lot-part-information.html#expressionsDeadlineSection"></a><br>Deadline Receipt Expressions</p><p><i>BT-630:</i> The time limit for receipt of expressions of interest.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='Lot']/cac:TenderingProcess/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:InterestExpressionReceptionPeriod/cbc:EndTime</span></code>
        </td>
        <td class="mapping">

<a href="operations.md#get-the-lot-for-a-procurementprojectlot">Get the lot for the ProcurementProjectLot</a>, combine with <a href="#BT-630(d)-lot">BT-630(d)-Lot</a>, <a href="operations.md#convert-a-date-to-iso-format">convert date to ISO format</a> and map to the lot's `tenderPeriod.endDate`.

```xml
<efac:InterestExpressionReceptionPeriod>
  <cbc:EndTime>18:00:00+01:00</cbc:EndTime>
</efac:InterestExpressionReceptionPeriod>
```

```json
{
  "tender": {
    "lots": [
      {
        "tenderPeriod": {
          "endDate": "2019-10-28T18:00:00+01:00"
        }
      }
    ]
  }
}
```

</td>
      </tr>
      <tr id="BT-631-Lot">
        <td class="field break-all">
            <p><b>BT-631-Lot</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/procedure-lot-part-information.html#interestInvitationSection"></a><br>Dispatch Invitation Interest</p><p><i>BT-631:</i> The estimated date of dispatch of the invitations to confirm interest.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='Lot']/cac:TenderingProcess/cac:ParticipationInvitationPeriod/cbc:StartDate</span></code>
        </td>
        <td class="mapping">

<a href="operations.md#get-the-lot-for-a-procurementprojectlot">Get the lot for the ProcurementProjectLot</a>, <a href="operations.md#convert-a-date-to-iso-format">convert date to ISO format</a> and map to the lot's `.communication.invitationToConfirmInterest`.

```xml
<cac:ParticipationInvitationPeriod>
  <cbc:StartDate>2019-11-15+01:00</cbc:StartDate>
</cac:ParticipationInvitationPeriod>
```

```json
{
  "tender": {
    "lots": [
      {
        "communication": {
          "invitationToConfirmInterest": "2019-11-15T09:00:00+01:00"
        }
      }
    ]
  }
}
```

</td>
      </tr>
      <tr id="BT-632-Lot">
        <td class="field break-all">
            <p><b>BT-632-Lot</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/procedure-lot-part-information.html#toolNameSection"></a><br>Tool Name</p><p><i>BT-632:</i> The name of the electronic tool or device used for electronic communication.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='Lot']/cac:TenderingProcess/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efbc:AccessToolName</span></code>
        </td>
        <td class="mapping">

<a href="operations.md#get-the-lot-for-a-procurementprojectlot">Get the lot for the ProcurementProjectLot</a> and map to its `.communication.atypicalToolName`.

```xml
<efext:EformsExtension>
  <efbc:AccessToolName>AbcKomSoft</efbc:AccessToolName>
</efext:EformsExtension>
```

```json
{
  "tender": {
    "lots": [
      {
        "communication": {
          "atypicalToolName": "AbcKomSoft"
        }
      }
    ]
  }
}
```

</td>
      </tr>
      <tr id="BT-632-Part">
        <td class="field break-all">
            <p><b>BT-632-Part</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/procedure-lot-part-information.html#toolNameSection"></a><br>Tool Name</p><p><i>BT-632:</i> The name of the electronic tool or device used for electronic communication.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='Part']/cac:TenderingProcess/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efbc:AccessToolName</span></code>
        </td>
        <td class="mapping">

Map to `tender.communication.atypicalToolName`.

```xml
<efext:EformsExtension>
  <efbc:AccessToolName>AbcKomSoft</efbc:AccessToolName>
</efext:EformsExtension>
```

```json
{
  "tender": {
    "communication": {
      "atypicalToolName": "AbcKomSoft"
    }
  }
}
```

</td>
      </tr>
      <tr id="BT-633-Organization">
        <td class="field break-all">
            <p><b>BT-633-Organization</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/parties.html#_general_structure_of_an_organization_related_information"></a><br>Organisation Natural Person</p><p><i>BT-633:</i> The organisation is a natural person.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:Organizations/efac:Organization/efbc:NaturalPersonIndicator</span></code>
        </td>
        <td class="mapping">

<a href="operations.md#get-the-organization-for-a-company">Get the organization for the company</a> and set it's `details.scale` to 'selfEmployed'.

```xml
<efac:Organization>
  <efbc:NaturalPersonIndicator>false</efbc:NaturalPersonIndicator>
</efac:Organization>
```

```json
{
  "parties": [
    {
      "details": {
        "scale": "selfEmployed"
      }
    }
  ]
}
```

</td>
      </tr>
      <tr id="BT-634-Lot">
        <td class="field break-all">
            <p><b>BT-634-Lot</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/procedure-lot-part-information.html#procurementRelaunchSection"></a><br>Procurement Relaunch</p><p><i>BT-634:</i> This cancelled or unsuccessful procedure or lot will be relaunched.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='Lot']/cac:TenderingProcess/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efbc:ProcedureRelaunchIndicator</span></code>
        </td>
        <td class="mapping">

Discard.

```xml
<efext:EformsExtension>
  <efbc:ProcedureRelaunchIndicator>true</efbc:ProcedureRelaunchIndicator>
</efext:EformsExtension>
```



</td>
      </tr>
      <tr id="BT-634-Procedure">
        <td class="field break-all">
            <p><b>BT-634-Procedure</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/procedure-lot-part-information.html#procurementRelaunchSection"></a><br>Procurement Relaunch</p><p><i>BT-634:</i> This cancelled or unsuccessful procedure or lot will be relaunched.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:TenderingProcess/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efbc:ProcedureRelaunchIndicator</span></code>
        </td>
        <td class="mapping">

Discard.

```xml
<efext:EformsExtension>
  <efbc:ProcedureRelaunchIndicator>true</efbc:ProcedureRelaunchIndicator>
</efext:EformsExtension>
```



</td>
      </tr>
      <tr id="BT-635-LotResult">
        <td class="field break-all">
            <p><b>BT-635-LotResult</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/competition-results.html#_lot_result"></a><br>Buyer Review Requests Count</p><p><i>BT-635:</i> The number of requests the buyer received to review any of its decisions.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:NoticeResult/efac:LotResult/efac:AppealRequestsStatistics[efbc:StatisticsCode/@listName='irregularity-type']/efbc:StatisticsNumeric</span></code>
        </td>
        <td class="mapping">

This field maps to the same `Statistic` objects as created for BT-636-LotResult. For each `AppealRequestStatistics`, <a href="operations.md#add-a-statistic">add a statistic</a> or update the corresponding `Statistic` object and map to its `.value`.

```xml
<efac:AppealRequestsStatistics>
  <efbc:StatisticsNumeric>2</efbc:StatisticsNumeric>
</efac:AppealRequestsStatistics>
```

```json
{
  "statistics": [
    {
      "id": "1",
      "value": "2",
      "scope": "complaints"
    }
  ]
}
```

</td>
      </tr>
      <tr id="BT-636-LotResult">
        <td class="field break-all">
            <p><b>BT-636-LotResult</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/competition-results.html#_lot_result"></a><br>Buyer Review Requests Irregularity Type</p><p><i>BT-636:</i> The type of irregularity alleged in the review requests.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:NoticeResult/efac:LotResult/efac:AppealRequestsStatistics[efbc:StatisticsCode/@listName='irregularity-type']/efbc:StatisticsCode</span></code>
        </td>
        <td class="mapping">

This field maps to the same `Statistic` objects as created for BT-635-LotResult. For each `AppealRequestStatistics`, <a href="operations.md#add-a-statistic">add a statistic</a> or update the corresponding `Statistic` object and map to its `.measure`. Look up the code's label in the <a href="https://op.europa.eu/en/web/eu-vocabularies/concept-scheme/-/resource?uri=http://publications.europa.eu/resource/authority/irregularity-type">authority table</a> and map it to `.notes`

```xml
<efac:AppealRequestsStatistics>
  <efbc:StatisticsCode listName="irregularity-type">unj-lim-subc</efbc:StatisticsCode>
</efac:AppealRequestsStatistics>
```

```json
{
  "statistics": [
    {
      "id": "1",
      "measure": "ab-low",
      "scope": "complaints",
      "notes": "Unjustified rejection of abnormally low tenders"
    }
  ]
}
```

</td>
      </tr>
      <tr id="BT-64-Lot">
        <td class="field break-all">
            <p><b>BT-64-Lot</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/procedure-lot-part-information.html#subcontractingObligationSection"></a><br>Subcontracting Obligation Minimum</p><p><i>BT-64:</i> The minimum percentage of the contract value that the contractor must subcontract using the competitive procedure described in Title III of European Parliament and Council Directive 2009/81/EC.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='Lot']/cac:TenderingTerms/cac:AllowedSubcontractTerms/cbc:MinimumPercent</span></code>
        </td>
        <td class="mapping">

<a href="operations.md#get-the-lot-for-a-procurementprojectlot">Get the lot for the ProcurementProjectLot</a> and map to its `.subcontracting.competitiveMinimumPercentage`.

```xml
<cac:AllowedSubcontractTerms>
  <cbc:MinimumPercent>25.5</cbc:MinimumPercent>
</cac:AllowedSubcontractTerms>
```

```json
{
  "tender": {
    "lots": [
      {
        "subcontracting": {
          "competitiveMinimumPercentage": 25.5
        }
      }
    ]
  }
}
```

</td>
      </tr>
      <tr id="BT-644-Lot">
        <td class="field break-all">
            <p><b>BT-644-Lot</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/procedure-lot-part-information.html#prizeSection"></a><br>Prize Value</p><p><i>BT-644:</i> The value of the prize, if any, for the winner of a design contest, innovation partnership or competitive dialogue</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='Lot']/cac:TenderingTerms/cac:AwardingTerms/cac:Prize/cbc:ValueAmount</span></code>
        </td>
        <td class="mapping">

This field maps to the same `Prize` objects as created for BT-44-Lot and BT-45-Lot.

<a href="operations.md#get-the-lot-for-a-procurementprojectlot">Get the lot for the ProcurementProjectLot</a>.
For each `cac:Prize` add or update the corresponding `Prize` object in the lot's `designContest.prize.details` array and map to its `value.amount`. Map `@currencyID` to the value's `.currency`.

```xml
<cac:Prize>
  <cbc:ValueAmount currencyID="EUR">5000</cbc:ValueAmount>
</cac:Prize>
```

```json
{
  "tender": {
    "lots": [
      {
        "designContest": {
          "prizes": {
            "details": [
              {
                "value": {
                  "amount": 5000,
                  "currency": "EUR"
                }
              }
            ]
          }
        }
      }
    ]
  }
}
```

</td>
      </tr>
      <tr id="BT-65-Lot">
        <td class="field break-all">
            <p><b>BT-65-Lot</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/procedure-lot-part-information.html#subcontractingObligationSection"></a><br>Subcontracting Obligation</p><p><i>BT-65:</i> An obligation to be met by the tenderer concerning subcontracting.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='Lot']/cac:TenderingTerms/cac:AllowedSubcontractTerms[cbc:SubcontractingConditionsCode/@listName='subcontracting-obligation']/cbc:SubcontractingConditionsCode</span></code>
        </td>
        <td class="mapping">

If different from 'none':

- <a href="operations.md#get-the-lot-for-a-procurementprojectlot">Get the lot for the ProcurementProjectLot</a>.
- Look up the code's label in the <a href="https://op.europa.eu/en/web/eu-vocabularies/concept-scheme/-/resource?uri=http://publications.europa.eu/resource/authority/subcontracting-obligation">authority table</a> and map it to the lot's `.subcontracting.description`.

```xml
<cac:AllowedSubcontractTerms>
  <cbc:SubcontractingConditionsCode listName="subcontracting-obligation">subc-min</cbc:SubcontractingConditionsCode>
</cac:AllowedSubcontractTerms>
```

```json
{
  "tender": {
    "lots": [
      {
        "subcontracting": {
          "description": "The contractor must subcontract a minimum percentage of the contract using the procedure set out in Title III of Directive 2009/81/EC."
        }
      }
    ]
  }
}
```

</td>
      </tr>
      <tr id="BT-651-Lot">
        <td class="field break-all">
            <p><b>BT-651-Lot</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/procedure-lot-part-information.html#subcontractingObligationSection"></a><br>Subcontracting Tender Indication</p><p><i>BT-651:</i> The information about subcontracting that must be indicated in the tender.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='Lot']/cac:TenderingTerms/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:TenderSubcontractingRequirements/efbc:TenderSubcontractingRequirementsCode</span></code>
        </td>
        <td class="mapping">

<a href="operations.md#get-the-lot-for-a-procurementprojectlot">Get the lot for the ProcurementProjectLot</a> and add to the lot's `.submissionTerms.subcontractingClauses` array.

```xml
<efac:TenderSubcontractingRequirements>
  <efbc:TenderSubcontractingRequirementsCode listName="subcontracting-indication">subc-oblig</efbc:TenderSubcontractingRequirementsCode>
</efac:TenderSubcontractingRequirements>
```

```json
{
  "tender": {
    "lots": [
      {
        "submissionTerms": {
          "subcontractingClauses": "subc-oblig"
        }
      }
    ]
  }
}
```

</td>
      </tr>
      <tr id="BT-660-LotResult">
        <td class="field break-all">
            <p><b>BT-660-LotResult</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/competition-results.html#_lot_result"></a><br>Framework Re-estimated Value</p><p><i>BT-660:</i> The value likely to be spent within a framework agreement over its whole duration, including options and renewals, as re-estimated on the basis of the winner’s tender or winners’ tenders.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:NoticeResult/efac:LotResult/efac:FrameworkAgreementValues/efbc:ReestimatedValueAmount</span></code>
        </td>
        <td class="mapping">

<a href="operations.md#get-the-award-for-a-lotresult">Get the award for the LotResult</a> and map to the award's `.estimatedValue.amount`. Map `@currencyID` to the value's `.currency`.

```xml
<efac:FrameworkAgreementValues>
  <cbc:ReestimatedValueAmount currencyID="EUR">123</cbc:ReestimatedValueAmount>
</efac:FrameworkAgreementValues>
```

```json
{
  "awards": [
    {
      "estimatedValue": {
        "amount": 123,
        "currency": "EUR"
      }
    }
  ]
}
```

</td>
      </tr>
      <tr id="BT-661-Lot">
        <td class="field break-all">
            <p><b>BT-661-Lot</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/procedure-lot-part-information.html#maxCandidatesSection"></a><br>Maximum Candidates Indicator</p><p><i>BT-661:</i> There is a maximum number of candidates to be invited for the second stage of the procedure.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='Lot']/cac:TenderingProcess/cac:EconomicOperatorShortList/cbc:LimitationDescription</span></code>
        </td>
        <td class="mapping">

Discard.

```xml
<cac:EconomicOperatorShortList>
  <cbc:LimitationDescription>true</cbc:LimitationDescription>
</cac:EconomicOperatorShortList>
```



</td>
      </tr>
      <tr id="BT-67(a)-Procedure">
        <td class="field break-all">
            <p><b>BT-67(a)-Procedure</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/procedure-lot-part-information.html#reservedParticipationSection"></a><br>Exclusion Grounds</p><p><i>BT-67:</i> The brief description of criteria regarding the personal situation of tenderers that may lead to their exclusion. This shall include a list of all such criteria and indicate required information (e.g. self-declaration, documentation). This may also include specific national exclusion grounds. </p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:TenderingTerms/cac:TendererQualificationRequest/cac:SpecificTendererRequirement/cbc:TendererRequirementTypeCode[@listName='exclusion-ground']</span></code>
        </td>
        <td class="mapping">

Add an `SelectionCriterion` object to the `tender.exclusionGrounds` array and map to its `.type`.

```xml
<cac:SpecificTendererRequirement>
  <cbc:TendererRequirementTypeCode listName="exclusion-ground">CRITERION.EXCLUSION.NATIONAL.OTHER</cbc:TendererRequirementTypeCode>
</cac:SpecificTendererRequirement>
```

```json
{
  "tender": {
    "exclusionGrounds": [
      {
        "type": "CRITERION.EXCLUSION.NATIONAL.OTHER"
      }
    ]
  }
}
```

</td>
      </tr>
      <tr id="BT-67(b)-Procedure">
        <td class="field break-all">
            <p><b>BT-67(b)-Procedure</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/procedure-lot-part-information.html#reservedParticipationSection"></a><br>Exclusion Grounds</p><p><i>BT-67:</i> The brief description of criteria regarding the personal situation of tenderers that may lead to their exclusion. This shall include a list of all such criteria and indicate required information (e.g. self-declaration, documentation). This may also include specific national exclusion grounds. </p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:TenderingTerms/cac:TendererQualificationRequest/cac:SpecificTendererRequirement/cbc:Description</span></code>
        </td>
        <td class="mapping">

Map to the relevant `tender.exclusionGrounds` `SelectionCriterion` object's `.description`.

```xml
<cac:SpecificTendererRequirement>
  <cbc:Description languageID="ENG">Applicants not satisfying ...</cbc:Description>
</cac:SpecificTendererRequirement>
```

```json
{
  "tender": {
    "exclusionGrounds": [
      {
        "description": "Applicants not satisfying..."
      }
    ]
  }
}
```

</td>
      </tr>
      <tr id="BT-70-Lot">
        <td class="field break-all">
            <p><b>BT-70-Lot</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/procedure-lot-part-information.html#termsPerformanceSection"></a><br>Terms Performance</p><p><i>BT-70:</i> The main information about the performance of the contract (e.g. intermediary deliverables, compensation for damages, intellectual property rights).</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='Lot']/cac:TenderingTerms/cac:ContractExecutionRequirement[cbc:ExecutionRequirementCode/@listName='conditions']/cbc:Description</span></code>
        </td>
        <td class="mapping">

<a href="operations.md#get-the-lot-for-a-procurementprojectlot">Get the lot for the ProcurementProjectLot</a> and map to its `.contractTerms.performanceTerms`.

```xml
<cac:ContractExecutionRequirement>
  <cbc:ExecutionRequirementCode listName="conditions">performance</cbc:ExecutionRequirementCode>
  <cbc:Description languageID="ENG">During execution of the contract, ...</cbc:Description>
</cac:ContractExecutionRequirement>
```

```json
{
  "tender": {
    "lots": [
      {
        "contractTerms": {
          "performanceTerms": "During execution of the contract, ..."
        }
      }
    ]
  }
}
```

</td>
      </tr>
      <tr id="BT-701-notice">
        <td class="field break-all">
            <p><b>BT-701-notice</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/notice-information.html#noticeIDSection"></a><br>Notice Identifier</p><p><i>BT-701:</i> The European Public Procurement Notice Identifier of this notice. Including this identifier in all published version of this notice (e.g. TED, national publication portals, regional publication portals) allows unique identification of procurement notices around the Union.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cbc:ID[@schemeName='notice-id']</span></code>
        </td>
        <td class="mapping">

<a href="operations.md#create-a-release">Create a new release</a>

```xml
<cbc:ID schemeName="notice-id">0f56d80f-8a5f-4876-8e24-feaa766c456d</cbc:ID>
```



</td>
      </tr>
      <tr id="BT-702(a)-notice">
        <td class="field break-all">
            <p><b>BT-702(a)-notice</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/notice-information.html#noticeLanguageSection"></a><br>Notice Official Language</p><p><i>BT-702:</i> The language(s) in which this notice is officially available. These linguistic versions are equally legally valid.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cbc:NoticeLanguageCode</span></code>
        </td>
        <td class="mapping">

Lowercase `/*/cbc:NoticeLanguageCode` and convert the code into a two-letter <a href="https://en.wikipedia.org/wiki/List_of_ISO_639-1_codes">ISO 639-1 code</a>, and map to `language`.

Discard `/*/cac:AdditionalNoticeLanguage/cbc:ID`.

```xml
<cbc:NoticeLanguageCode>ENG</cbc:NoticeLanguageCode>
```

```json
{
  "language": "en"
}
```

</td>
      </tr>
      <tr id="BT-702(b)-notice">
        <td class="field break-all">
            <p><b>BT-702(b)-notice</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/notice-information.html#noticeLanguageSection"></a><br>Notice Official Language</p><p><i>BT-702:</i> The language(s) in which this notice is officially available. These linguistic versions are equally legally valid.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:AdditionalNoticeLanguage/cbc:ID</span></code>
        </td>
        <td class="mapping">

Discard `/*/cac:AdditionalNoticeLanguage/cbc:ID`.

```xml
<cac:AdditionalNoticeLanguage>
  <cbc:ID>FRA</cbc:ID>
</cac:AdditionalNoticeLanguage>
```



</td>
      </tr>
      <tr id="BT-706-UBO">
        <td class="field break-all">
            <p><b>BT-706-UBO</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/parties.html#ultimateBeneficialOwnerSection"></a><br>Winner Owner Nationality</p><p><i>BT-706:</i> The nationality (or nationalities) of the beneficiary owner(s) of the winner, tenderer, or subcontractor as published in the register(s) established by European Parliament and Council Directive (EU) 2018/843. If such a register does not exist (e.g. in case of contractors established outside the Union) then equivalent information from other sources.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:Organizations/efac:UltimateBeneficialOwner/efac:Nationality/cbc:NationalityID</span></code>
        </td>
        <td class="mapping">

<a href="operations.md#get-the-person-for-an-ultimate-beneficial-owner">Get the person for the ultimate beneficial owner</a>, look up the equivalent ISO 3166-1 alpha-2 code in the <a href="https://op.europa.eu/en/web/eu-vocabularies/concept-scheme/-/resource?uri=http://publications.europa.eu/resource/authority/country">authority table</a> and map to the person's `.nationality`.

```xml
<efac:UltimateBeneficialOwner>
  <efac:Nationality>
    <cbc:NationalityID>DEU</cbc:NationalityID>
  </efac:Nationality>
</efac:UltimateBeneficialOwner>
```

```json
{
  "parties": [
    {
      "beneficialOwners": [
        {
          "nationality": "DE"
        }
      ]
    }
  ]
}
```

</td>
      </tr>
      <tr id="BT-707-Lot">
        <td class="field break-all">
            <p><b>BT-707-Lot</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/procedure-lot-part-information.html#procurementDocsSection"></a><br>Documents Restricted Justification</p><p><i>BT-707:</i> The justification for restricting access to certain procurement documents.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='Lot']/cac:TenderingTerms/cac:CallForTendersDocumentReference[cbc:DocumentType/text()='restricted-document']/cbc:DocumentTypeCode</span></code>
        </td>
        <td class="mapping">

This field maps to the same `ParticipationFee` objects as created for BT-14-Lot and BT-615-Lot.

- <a href="operations.md#get-the-lot-for-a-procurementprojectlot">Get the lot for the ProcurementProjectLot</a>.
- For each `cac:CallForTendersDocumentReference`, add or update the corresponding `ParticipationFee` object in the lot's `.participationFees` array.
- Look up the code's label in the <a href="https://op.europa.eu/en/web/eu-vocabularies/concept-scheme/-/resource?uri=http://publications.europa.eu/resource/authority/communication-justification">authority table</a> and map it to the `ParticipationFee` object's `.description`.

```xml
<cac:CallForTendersDocumentReference>
  <cbc:DocumentTypeCode listName="communication-justification">ipr-iss</cbc:DocumentTypeCode>
</cac:CallForTendersDocumentReference>
```

```json
{
  "tender": {
    "lots": [
      {
        "participationFees": [
          {
            "description": "Intellectual property right issues"
          }
        ]
      }
    ]
  }
}
```

</td>
      </tr>
      <tr id="BT-707-Part">
        <td class="field break-all">
            <p><b>BT-707-Part</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/procedure-lot-part-information.html#procurementDocsSection"></a><br>Documents Restricted Justification</p><p><i>BT-707:</i> The justification for restricting access to certain procurement documents.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='Part']/cac:TenderingTerms/cac:CallForTendersDocumentReference[cbc:DocumentType/text()='restricted-document']/cbc:DocumentTypeCode</span></code>
        </td>
        <td class="mapping">

This field maps to the same `ParticipationFee` objects as created for BT-14-Part and BT-615-Part.

- For each `cac:CallForTendersDocumentReference`, add or update the corresponding `ParticipationFee` object in the `.participationFees` array.
- Look up the code's label in the <a href="https://op.europa.eu/en/web/eu-vocabularies/concept-scheme/-/resource?uri=http://publications.europa.eu/resource/authority/communication-justification">authority table</a> and map to the `ParticipationFee` object's `.description`.

```xml
<cac:CallForTendersDocumentReference>
  <cbc:DocumentTypeCode listName="communication-justification">ipr-iss</cbc:DocumentTypeCode>
</cac:CallForTendersDocumentReference>
```

```json
{
  "tender": {
    "participationFees": [
      {
        "description": "Intellectual property right issues"
      }
    ]
  }
}
```

</td>
      </tr>
      <tr id="BT-708-Lot">
        <td class="field break-all">
            <p><b>BT-708-Lot</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/procedure-lot-part-information.html#procurementDocsSection"></a><br>Documents Official Language</p><p><i>BT-708:</i> The language(s) in which the procurement documents are officially available. These linguistic versions are equally legally valid.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='Lot']/cac:TenderingTerms/cac:CallForTendersDocumentReference/cbc:LanguageID[not(../cbc:DocumentStatusCode/text()='non-official')]</span></code>
        </td>
        <td class="mapping">

<a href="operations.md#get-the-document-for-a-document-reference">Get the document for the document reference</a>.

Lowercase and convert the code into a two-letter <a href="https://en.wikipedia.org/wiki/List_of_ISO_639-1_codes">ISO 639-1 code</a> and add it to the document's `.languages` array.

<a href="operations.md#get-the-lot-for-a-procurementprojectlot">Get the lot for the ProcurementProjectLot</a> and add it to the document's `.relatedLots`.

```xml
<cac:ProcurementProjectLot>
  <cbc:ID schemeName="Lot">LOT-0001</cbc:ID>
  <cac:TenderingTerms>
    <cac:CallForTendersDocumentReference>
      <cbc:ID>20210521/CTFD/ENG/7654-02</cbc:ID>
      <cbc:LanguageID>ENG</cbc:LanguageID>
    </cac:CallForTendersDocumentReference>
  </cac:TenderingTerms>
</cac:ProcurementProjectLot>
```

```json
{
  "tender": {
    "documents": [
      {
        "id": "20210521/CTFD/ENG/7654-02",
        "languages": [
          "en"
        ],
        "relatedLots": [
          "LOT-0001"
        ]
      }
    ]
  }
}
```

</td>
      </tr>
      <tr id="BT-708-Part">
        <td class="field break-all">
            <p><b>BT-708-Part</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/procedure-lot-part-information.html#procurementDocsSection"></a><br>Documents Official Language</p><p><i>BT-708:</i> The language(s) in which the procurement documents are officially available. These linguistic versions are equally legally valid.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='Part']/cac:TenderingTerms/cac:CallForTendersDocumentReference/cbc:LanguageID[not(../cbc:DocumentStatusCode/text()='non-official')]</span></code>
        </td>
        <td class="mapping">

<a href="operations.md#get-the-document-for-a-document-reference">Get the document for the document reference</a>.

Lowercase and convert the code into a two-letter <a href="https://en.wikipedia.org/wiki/List_of_ISO_639-1_codes">ISO 639-1 code</a>.

Add it to the document's `.languages` array.

```xml
<cac:CallForTendersDocumentReference>
  <cbc:ID>20210521/CTFD/ENG/7654-02</cbc:ID>
  <cbc:LanguageID>ENG</cbc:LanguageID>
</cac:CallForTendersDocumentReference>
```

```json
{
  "tender": {
    "documents": [
      {
        "id": "20210521/CTFD/ENG/7654-02",
        "languages": [
          "en"
        ]
      }
    ]
  }
}
```

</td>
      </tr>
      <tr id="BT-709-LotResult">
        <td class="field break-all">
            <p><b>BT-709-LotResult</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/competition-results.html#_lot_result"></a><br>Framework Maximum Value</p><p><i>BT-709:</i> The maximum value which can be spent within a framework agreement over its whole duration, including options and renewals, as calculated on the basis of the winner’s tender or winners’ tenders.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:NoticeResult/efac:LotResult/efac:FrameworkAgreementValues/cbc:MaximumValueAmount</span></code>
        </td>
        <td class="mapping">

<a href="operations.md#get-the-award-for-a-lotresult">Get the award for the LotResult</a> and map to the award's `.maximumValue.amount`. Map `@currencyID` to the value's `.currency`.

```xml
<efac:FrameworkAgreementValues>
  <cbc:MaximumValueAmount currencyID="EUR">5000</cbc:MaximumValueAmount>
</efac:FrameworkAgreementValues>
```

```json
{
  "awards": [
    {
      "maximumValue": {
        "amount": 5000,
        "currency": "EUR"
      }
    }
  ]
}
```

</td>
      </tr>
      <tr id="BT-71-Lot">
        <td class="field break-all">
            <p><b>BT-71-Lot</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/procedure-lot-part-information.html#reservedParticipationSection"></a><br>Reserved Participation</p><p><i>BT-71:</i> Whether participation is reserved for specific organisations (e.g. sheltered workshops, organisations pursuing a public service mission).</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='Lot']/cac:TenderingTerms/cac:TendererQualificationRequest[not(cbc:CompanyLegalFormCode)][not(cac:SpecificTendererRequirement/cbc:TendererRequirementTypeCode[@listName='missing-info-submission'])]/cac:SpecificTendererRequirement[cbc:TendererRequirementTypeCode/@listName='reserved-procurement']/cbc:TendererRequirementTypeCode[@listName='reserved-procurement']</span></code>
        </td>
        <td class="mapping">

<a href="operations.md#get-the-lot-for-a-procurementprojectlot">Get the lot for the ProcurementProjectLot</a>.

If "res-pub-ser", add 'publicServiceMissionOrganization' to the lot's `.otherRequirements.reservedParticipation` array. If "res-ws", add 'shelteredWorkshop' to the lot's `.otherRequirements.reservedParticipation` array. If "none", discard.

```xml
<cac:SpecificTendererRequirement>
  <cbc:TendererRequirementTypeCode listName="reserved-procurement">res-ws</cbc:TendererRequirementTypeCode>
</cac:SpecificTendererRequirement>
```

```json
{
  "tender": {
    "lots": [
      {
        "otherRequirements": {
          "reservedParticipation": [
            "shelteredWorkshop"
          ]
        }
      }
    ]
  }
}
```

</td>
      </tr>
      <tr id="BT-71-Part">
        <td class="field break-all">
            <p><b>BT-71-Part</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/procedure-lot-part-information.html#reservedParticipationSection"></a><br>Reserved Participation</p><p><i>BT-71:</i> Whether participation is reserved for specific organisations (e.g. sheltered workshops, organisations pursuing a public service mission).</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='Part']/cac:TenderingTerms/cac:TendererQualificationRequest[not(cbc:CompanyLegalFormCode)][not(cac:SpecificTendererRequirement/cbc:TendererRequirementTypeCode[@listName='missing-info-submission'])]/cac:SpecificTendererRequirement[cbc:TendererRequirementTypeCode/@listName='reserved-procurement']/cbc:TendererRequirementTypeCode[@listName='reserved-procurement']</span></code>
        </td>
        <td class="mapping">

If `@TendererRequirementTypeCode` is "res-pub-ser", add 'publicServiceMissionOrganization' to `tender.otherRequirements.reservedParticipation` array. If `@TendererRequirementTypeCode` is "res-ws", add 'shelteredWorkshop' to `tender.otherRequirements.reservedParticipation` array. If `@TendererRequirementTypeCode` is "none", discard.

```xml
<cac:SpecificTendererRequirement>
  <cbc:TendererRequirementTypeCode listName="reserved-procurement">res-ws</cbc:TendererRequirementTypeCode>
</cac:SpecificTendererRequirement>
```

```json
{
  "tender": {
    "otherRequirements": {
      "reservedParticipation": [
        "shelteredWorkshop"
      ]
    }
  }
}
```

</td>
      </tr>
      <tr id="BT-710-LotResult">
        <td class="field break-all">
            <p><b>BT-710-LotResult</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/competition-results.html#_lot_result"></a><br>Tender Value Lowest</p><p><i>BT-710:</i> Value of the admissible tender with the lowest value. A tender shall be considered admissible where it has been submitted by a tenderer, who has not been excluded and who meets the selection criteria, and when it is in conformity with the technical specifications without being irregular (e.g. received late, having an abnormally low price or cost) or unacceptable or unsuitable. Only tenders for which it has been verified if they are admissible or inadmissible may be taken into account.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:NoticeResult/efac:LotResult/cbc:LowerTenderAmount</span></code>
        </td>
        <td class="mapping">

<a href="operations.md#add-a-statistic">Add a bids statistic</a>, set its `.measure` to 'lowestValidBidValue', map to its `.value`.

Map `@currencyID` to its `.currency`.

<a href="operations.md#get-the-lot-for-a-lotresult">Get the lot for the LotResult</a> and add the lot's `.id` to the statistic's `.relatedLots`.

```xml
<efac:LotResult>
  <cbc:LowerTenderAmount currencyID="EUR">1230000</cbc:LowerTenderAmount>
</efac:LotResult>
```

```json
{
  "bids": {
    "statistics": [
      {
        "measure": "lowestValidBidValue",
        "value": 1230000,
        "currency": "EUR",
        "relatedLot": "LOT-0001"
      }
    ]
  }
}
```

</td>
      </tr>
      <tr id="BT-711-LotResult">
        <td class="field break-all">
            <p><b>BT-711-LotResult</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/competition-results.html#_lot_result"></a><br>Tender Value Highest</p><p><i>BT-711:</i> Value of the admissible tender with the highest value. A tender shall be considered admissible where it has been submitted by a tenderer, who has not been excluded and who meets the selection criteria, and when it is in conformity with the technical specifications without being irregular (e.g. received late, having an abnormally low price or cost) or unacceptable or unsuitable. Only tenders for which it has been verified if they are admissible or inadmissible may be taken into account.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:NoticeResult/efac:LotResult/cbc:HigherTenderAmount</span></code>
        </td>
        <td class="mapping">

<a href="operations.md#add-a-statistic">Add a bids statistic</a>, set its `.measure` to 'highestValidBidValue', and map to its `.value`.

Map `@currencyID` to its `.currency`.

<a href="operations.md#get-the-lot-for-a-lotresult">Get the lot for the LotResult</a> and add the lot's `.id` to the statistic's `.relatedLots`.

```xml
<efac:LotResult>
  <cbc:HigherTenderAmount currencyID="EUR">456</cbc:HigherTenderAmount>
</efac:LotResult>
```

```json
{
  "bids": {
    "statistics": [
      {
        "measure": "highestValidBidValue",
        "value": 456,
        "currency": "EUR",
        "relatedLot": "LOT-0001"
      }
    ]
  }
}
```

</td>
      </tr>
      <tr id="BT-712(a)-LotResult">
        <td class="field break-all">
            <p><b>BT-712(a)-LotResult</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/competition-results.html#_lot_result"></a><br>Buyer Review Complainants (Code)</p><p><i>BT-712:</i> The number of organisations that requested the buyer to review any of its decisions (e.g. the technical specifications, award decision).</p>
            <code class="docutils literal notranslate"><span class="pre">/*/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:NoticeResult/efac:LotResult/efac:AppealRequestsStatistics[efbc:StatisticsCode/@listName='review-type']/efbc:StatisticsCode</span></code>
        </td>
        <td class="mapping">

This field maps to the same `Statistic` objects as created for BT-712(b)-LotResult.

For each `ancestor::AppealRequestStatistics`, <a href="operations.md#add-a-statistic">add a complaints statistic</a> or update the corresponding `Statistic` object, and set its `.measure` to "complainants".

<a href="operations.md#get-the-lot-for-a-lotresult">Get the lot for the LotResult</a> and add the lot's `.id` to the statistic's `.relatedLots`.

```xml
<efac:AppealRequestsStatistics>
  <efbc:StatisticsCode listName="review-type">complainants</efbc:StatisticsCode>
</efac:AppealRequestsStatistics>
```

```json
{
  "statistics": [
    {
      "id": "1",
      "value": "2",
      "scope": "complaints"
    }
  ]
}
```

</td>
      </tr>
      <tr id="BT-712(b)-LotResult">
        <td class="field break-all">
            <p><b>BT-712(b)-LotResult</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/competition-results.html#_lot_result"></a><br>Buyer Review Complainants (Number)</p><p><i>BT-712:</i> The number of organisations that requested the buyer to review any of its decisions (e.g. the technical specifications, award decision).</p>
            <code class="docutils literal notranslate"><span class="pre">/*/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:NoticeResult/efac:LotResult/efac:AppealRequestsStatistics[efbc:StatisticsCode/@listName='review-type']/efbc:StatisticsNumeric</span></code>
        </td>
        <td class="mapping">

This field maps to the same `Statistic` objects as created for BT-712(a)-LotResult.

For each `ancestor::AppealRequestStatistics`, <a href="operations.md#add-a-statistic">add a complaints statistic</a> or update the corresponding `Statistic` object, and map to its `.value`.

<a href="operations.md#get-the-lot-for-a-lotresult">Get the lot for the LotResult</a> and add the lot's `.id` to the statistic's `.relatedLots`.

```xml
<efac:AppealRequestsStatistics>
  <efbc:StatisticsNumeric>2</efbc:StatisticsNumeric>
</efac:AppealRequestsStatistics>
```

```json
{
  "statistics": [
    {
      "id": "1",
      "value": "2",
      "measure": "complainants",
      "scope": "complaints"
    }
  ]
}
```

</td>
      </tr>
      <tr id="BT-717-Lot">
        <td class="field break-all">
            <p><b>BT-717-Lot</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/procedure-lot-part-information.html#CVDDirectiveLotSection"></a><br>Clean Vehicles Directive</p><p><i>BT-717:</i> The procurement falls within the scope of the European Parliament and Council 2009/33/EC (Clean Vehicles Directive – CVD).</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='Lot']/cac:TenderingTerms/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:StrategicProcurement/efbc:ApplicableLegalBasis</span></code>
        </td>
        <td class="mapping">

<a href="operations.md#get-the-lot-for-a-procurementprojectlot">Get the lot for the ProcurementProjectLot</a>. If "true", add 'EU-CVD' to the lot's `.coveredBy` array. If "false", discard.

```xml
<efac:StrategicProcurement>
  <efbc:ApplicableLegalBasis listName="cvd-scope">true</efbc:ApplicableLegalBasis>
</efac:StrategicProcurement>
```

```json
{
  "tender": {
    "lots": [
      {
        "coveredBy": [
          "EU-CVD"
        ]
      }
    ]
  }
}
```

</td>
      </tr>
      <tr id="BT-718-notice">
        <td class="field break-all">
            <p><b>BT-718-notice</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/change-notice.html#changeSection"></a><br>Change Procurement Documents</p><p><i>BT-718:</i> The procurement documents have changed.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:Changes/efac:Change/efbc:ProcurementDocumentsChangeIndicator</span></code>
        </td>
        <td class="mapping">

These values map to the same `Amendment` objects as created for BT-140. Update the corresponding `Amendment` object and map to its `.documentsChanged`.

```xml
<efac:Change>
  <efbc:ProcurementDocumentsChangeIndicator>true</efbc:ProcurementDocumentsChangeIndicator>
</efac:Change>
```

```json
{
  "tender": {
    "amendments": [
      {
        "documentsChanged": true
      }
    ]
  }
}
```

</td>
      </tr>
      <tr id="BT-719-notice">
        <td class="field break-all">
            <p><b>BT-719-notice</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/change-notice.html#changeSection"></a><br>Change Procurement Documents Date</p><p><i>BT-719:</i> The date and time when the procurement documents have changed.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:Changes/efac:Change/efbc:ProcurementDocumentsChangeDate</span></code>
        </td>
        <td class="mapping">

These values map to the same `Amendment` objects as created for BT-140. Update the corresponding `Amendment` object, <a href="operations.md#convert-a-date-to-iso-format">convert date to ISO format</a> and map to its `.documentsChangeDate`.

```xml
<efac:Change>
  <efbc:ProcurementDocumentsChangeDate>2019-10-24+01:00</efbc:ProcurementDocumentsChangeDate>
</efac:Change>
```

```json
{
  "tender": {
    "amendments": [
      {
        "documentsChangeDate": "2019-10-24T00:00:00+01:00"
      }
    ]
  }
}
```

</td>
      </tr>
      <tr id="BT-720-Tender">
        <td class="field break-all">
            <p><b>BT-720-Tender</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/competition-results.html#lotTenderSection"></a><br>Tender Value</p><p><i>BT-720:</i> The value of the tender or another result, including options and renewals. In case of the modification notice, the value of the modification.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:NoticeResult/efac:LotTender/cac:LegalMonetaryTotal/cbc:PayableAmount</span></code>
        </td>
        <td class="mapping">

<a href="operations.md#get-the-bid-for-a-lottender">Get the bid for the LotTender</a> and map to the bid's `.value`. Map `@currencyID` to the value's `.currency`.

```xml
<cac:LegalMonetaryTotal>
  <cbc:PayableAmount currencyID="EUR">500</cbc:PayableAmount>
</cac:LegalMonetaryTotal>
```

```json
{
  "bids": {
    "details": [
      {
        "value": {
          "amount": 500,
          "currency": "EUR"
        }
      }
    ]
  }
}
```

</td>
      </tr>
      <tr id="BT-721-Contract">
        <td class="field break-all">
            <p><b>BT-721-Contract</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/competition-results.html#settledContractSection"></a><br>Contract Title</p><p><i>BT-721:</i> The name of the contract or, in case of voluntary-ex ante transparency notices and design contest result notices, of the decision. </p>
            <code class="docutils literal notranslate"><span class="pre">/*/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:NoticeResult/efac:SettledContract/cbc:Title</span></code>
        </td>
        <td class="mapping">

<a href="operations.md#get-the-contract-for-a-settledcontract">Get the contract for the SettledContract</a> and map to the contract's `.title`.

```xml
<efac:SettledContract>
  <cbc:Title languageID="ENG">My contract title</cbc:Title>
</efac:SettledContract>
```

```json
{
  "contracts": [
    {
      "title": "My contract title"
    }
  ]
}
```

</td>
      </tr>
      <tr id="BT-722-Contract">
        <td class="field break-all">
            <p><b>BT-722-Contract</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/competition-results.html#settledContractSection"></a><br>Contract EU Funds Programme</p><p><i>BT-722:</i> The programme of the Union funds used to at least partially finance the contract.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:NoticeResult/efac:SettledContract/efac:Funding/cbc:FundingProgramCode</span></code>
        </td>
        <td class="mapping">

This field maps to the same `finance` objects as created for BT-5011 and BT-6110.
<a href="operations.md#get-the-contract-for-a-settledcontract">Get the contract for the SettledContract</a>.
For each `efac:Funding`, add or update the corresponding `Finance` object in the contract's `.finance` array and map to its `.title`.

```xml
<efac:Funding>
  <cbc:FundingProgramCode listName="eu-programme">ABC123</cbc:FundingProgramCode>
</efac:Funding>
```

```json
{
  "contracts": [
    {
      "finance": [
        {
          "title": "ABC123"
        }
      ]
    }
  ]
}
```

</td>
      </tr>
      <tr id="BT-7220-Lot">
        <td class="field break-all">
            <p><b>BT-7220-Lot</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/procedure-lot-part-information.html#EUFundsSection"></a><br>EU Funds Programme</p><p><i>BT-7220:</i> The programme of the Union funds used to at least partially finance the contract.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='Lot']/cac:TenderingTerms/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:Funding/cbc:FundingProgramCode</span></code>
        </td>
        <td class="mapping">

This field maps to the same `finance` objects as created for BT-5010-Lot and BT-6140-Lot.

If BT-5010-Lot is not present follow the guidance for BT-5010-Lot, setting the `.id` of the `Finance` object incrementally based on its position in the `finance` array rather than the value of BT-5010-Lot.

For each `ancestor::efac:Funding`, add or update the corresponding `Finance` object in the budget's `.finance` array and map to its `.title`.

```xml
<efac:Funding>
  <cbc:FundingProgramCode listName="eu-proramme">ERDF_2021</cbc:FundingProgramCode>
</efac:Funding>
```

```json
{
  "planning": {
    "budget": {
      "finance": [
        {
          "title": "ERDF_2021"
        }
      ]
    }
  }
}
```

</td>
      </tr>
      <tr id="BT-723-LotResult">
        <td class="field break-all">
            <p><b>BT-723-LotResult</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/competition-results.html#_lot_result"></a><br>Vehicle Category</p><p><i>BT-723:</i> The category of vehicle falling within the scope of Directive 2009/33/EC, including: Light-duty vehicles (M1, M2, N1); Bus (M3); Truck (N2, N3); M1; M2; N1; N2; N3.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:NoticeResult/efac:LotResult/efac:StrategicProcurement/efac:StrategicProcurementInformation/efac:ProcurementDetails/efbc:AssetCategoryCode</span></code>
        </td>
        <td class="mapping">

This field maps to the same `Item` objects as created for OPT-155-LotResult, OPT-156-LotResult and BT-735-LotResult. If no `Item` objects were created for `ancestor::efac:ProcurementDetails`:

- <a href="operations.md#get-the-award-for-a-lotresult">Get the award for the LotResult</a>.
- Add an `Item` object to its `items` array.
- Set the item's `.id` incrementally.

For each `ancestor::efac:ProcurementDetails/efac:StrategicProcurementStatistics/efbc:StatisticsCode` add a `Classification` object to the corresponding item's `additionalClassifications` array.

- Set the classification's `.scheme` to "vehicleCategory".
- Map the value of the field to the classification's `.id`.
- Look up the code's label in the <a href="https://op.europa.eu/en/web/eu-vocabularies/concept-scheme/-/resource?uri=http://publications.europa.eu/resource/authority/vehicle-category">authority table</a> and map it to the classification's `.description`.

```xml
<efac:ProcurementDetails>
  <efbc:AssetCategoryCode listName="vehicle-category">n2-n3</efbc:AssetCategoryCode>
</efac:ProcurementDetails>
```

```json
{
  "awards": [
    {
      "items": [
        {
          "id": "1",
          "additionalClassifications": [
            {
              "scheme": "vehicleCategory",
              "id": "n2-n3",
              "description": "Truck (N2-N3)"
            }
          ]
        }
      ]
    }
  ]
}
```

</td>
      </tr>
      <tr id="BT-726-Lot">
        <td class="field break-all">
            <p><b>BT-726-Lot</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/procedure-lot-part-information.html#suitableSMESection"></a><br>Suitable For SMEs</p><p><i>BT-726:</i> The buyer emphasizes that this procurement is also suitable for small and medium enterprises (SMEs).</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='Lot']/cac:ProcurementProject/cbc:SMESuitableIndicator</span></code>
        </td>
        <td class="mapping">

<a href="operations.md#get-the-lot-for-a-procurementprojectlot">Get the lot for the ProcurementProjectLot</a> and map to its `.suitability.sme`.

```xml
<cbc:SMESuitableIndicator>true</cbc:SMESuitableIndicator>
```

```json
{
  "tender": {
    "lots": [
      {
        "suitability": {
          "sme": true
        }
      }
    ]
  }
}
```

</td>
      </tr>
      <tr id="BT-726-LotsGroup">
        <td class="field break-all">
            <p><b>BT-726-LotsGroup</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/procedure-lot-part-information.html#suitableSMESection"></a><br>Suitable For SMEs</p><p><i>BT-726:</i> The buyer emphasizes that this procurement is also suitable for small and medium enterprises (SMEs).</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='LotsGroup']/cac:ProcurementProject/cbc:SMESuitableIndicator</span></code>
        </td>
        <td class="mapping">

<a href="operations.md#get-the-lot-group-for-a-procurementprojectlot">Get the lot group for the ProcurementProjectLot</a> and map to the lot group's `.suitability.sme`.

```xml
<cbc:SMESuitableIndicator>true</cbc:SMESuitableIndicator>
```

```json
{
  "tender": {
    "lotGroups": [
      {
        "suitability": {
          "sme": true
        }
      }
    ]
  }
}
```

</td>
      </tr>
      <tr id="BT-726-Part">
        <td class="field break-all">
            <p><b>BT-726-Part</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/procedure-lot-part-information.html#suitableSMESection"></a><br>Suitable For SMEs</p><p><i>BT-726:</i> The buyer emphasizes that this procurement is also suitable for small and medium enterprises (SMEs).</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='Part']/cac:ProcurementProject/cbc:SMESuitableIndicator</span></code>
        </td>
        <td class="mapping">

Map to `.tender.suitability.sme`.

```xml
<cbc:SMESuitableIndicator>true</cbc:SMESuitableIndicator>
```

```json
{
  "tender": {
    "suitability": {
      "sme": true
    }
  }
}
```

</td>
      </tr>
      <tr id="BT-727-Lot">
        <td class="field break-all">
            <p><b>BT-727-Lot</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/procedure-lot-part-information.html#performancePlaceSection"></a><br>Place Performance Services Other</p><p><i>BT-727:</i> There are other restrictions on the place of performance (e.g. "anywhere in the European Economic Area", "anywhere in the given country"). </p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='Lot']/cac:ProcurementProject/cac:RealizedLocation/cac:Address/cbc:Region</span></code>
        </td>
        <td class="mapping">

This field maps to the same `Address` objects as created for BT-728-Lot, BT-5121-Lot, BT-5071-Lot, BT-5131-Lot, BT-5101-Lot and BT-5141-Lot.

<a href="operations.md#get-the-item-for-a-procurementprojectlot">Get the item for the ProcurementProjectLot</a>.
For each `cac:RealizedLocation`, add or update the corresponding `Address` object in the item's `.deliveryAddresses` array.
Look up the code's label in the <a href="https://op.europa.eu/en/web/eu-vocabularies/concept-scheme/-/resource?uri=http://publications.europa.eu/resource/authority/other-place-service">authority table</a> and map it to the address's `.description`, concatenating to the existing entry in this field if necessary.

```xml
<cac:Address>
  <cbc:Region>anyw-eea</cbc:Region>
</cac:Address>
```

```json
{
  "tender": {
    "items": [
      {
        "deliveryLocations": [
          {
            "description": "Anywhere in the European Economic Area"
          }
        ]
      }
    ]
  }
}
```

</td>
      </tr>
      <tr id="BT-727-Part">
        <td class="field break-all">
            <p><b>BT-727-Part</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/procedure-lot-part-information.html#performancePlaceSection"></a><br>Place Performance Services Other</p><p><i>BT-727:</i> There are other restrictions on the place of performance (e.g. "anywhere in the European Economic Area", "anywhere in the given country"). </p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='Part']/cac:ProcurementProject/cac:RealizedLocation/cac:Address/cbc:Region</span></code>
        </td>
        <td class="mapping">

This field maps to the same `Address` objects as created for BT-728-Part, BT-5121-Part, BT-5131-Part, BT-5071-Part, BT-5101-Part and BT-5141-Part.
For each `cac:RealizedLocation`, add or update the corresponding `Address` object in the `tender.deliveryAddresses` array
Look up the code's label in the <a href="https://op.europa.eu/en/web/eu-vocabularies/concept-scheme/-/resource?uri=http://publications.europa.eu/resource/authority/other-place-service">authority table</a>, and map to the address's `.description`, concatenating to the existing entry in this field if necessary.

```xml
<cac:Address>
  <cbc:Region>anyw-eea</cbc:Region>
</cac:Address>
```

```json
{
  "tender": {
    "deliveryLocations": [
      {
        "description": "Anywhere in the European Economic Area"
      }
    ]
  }
}
```

</td>
      </tr>
      <tr id="BT-727-Procedure">
        <td class="field break-all">
            <p><b>BT-727-Procedure</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/procedure-lot-part-information.html#performancePlaceSection"></a><br>Place Performance Services Other</p><p><i>BT-727:</i> There are other restrictions on the place of performance (e.g. "anywhere in the European Economic Area", "anywhere in the given country"). </p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProject/cac:RealizedLocation/cac:Address/cbc:Region</span></code>
        </td>
        <td class="mapping">

This field maps to the same `Address` objects as created for BT-728-Procedure, BT-5121-Procedure, BT-5131-Procedure, BT-5071-Procedure, BT-5101-Procedure and BT-5141-Procedure.
For each `cac:RealizedLocation`, add or update the corresponding `Address` object in the `tender.deliveryAddresses` array
Look up the code's label in the <a href="https://op.europa.eu/en/web/eu-vocabularies/concept-scheme/-/resource?uri=http://publications.europa.eu/resource/authority/other-place-service">authority table</a>, and map to the address's `.description`, concatenating to the existing entry in this field if necessary.

```xml
<cac:Address>
  <cbc:Region>anyw-eea</cbc:Region>
</cac:Address>
```

```json
{
  "tender": {
    "deliveryLocations": [
      {
        "description": "Anywhere in the European Economic Area"
      }
    ]
  }
}
```

</td>
      </tr>
      <tr id="BT-728-Lot">
        <td class="field break-all">
            <p><b>BT-728-Lot</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/procedure-lot-part-information.html#performancePlaceSection"></a><br>Place Performance Additional Information</p><p><i>BT-728:</i> Additional information about the place of performance.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='Lot']/cac:ProcurementProject/cac:RealizedLocation/cbc:Description</span></code>
        </td>
        <td class="mapping">

This field maps to the same `Address` objects as created for BT-727-Lot, BT-5121-Lot, BT-5071-Lot, BT-5131-Lot, BT-5101-Lot and BT-5141-Lot.

<a href="operations.md#get-the-item-for-a-procurementprojectlot">Get the item for the ProcurementProjectLot</a>.
For each `cac:RealizedLocation`, add or update the corresponding `Address` object in the item's `.deliveryAddresses` array and map it to the address's `.description`, concatenating to the existing entry in this field if necessary.

```xml
<cac:RealizedLocation>
  <cbc:Description languageID="ENG">Further realizations ...</cbc:Description>
</cac:RealizedLocation>
```

```json
{
  "tender": {
    "items": [
      {
        "deliveryLocation": {
          "description": "Further realizations..."
        }
      }
    ]
  }
}
```

</td>
      </tr>
      <tr id="BT-728-Part">
        <td class="field break-all">
            <p><b>BT-728-Part</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/procedure-lot-part-information.html#performancePlaceSection"></a><br>Place Performance Additional Information</p><p><i>BT-728:</i> Additional information about the place of performance.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='Part']/cac:ProcurementProject/cac:RealizedLocation/cbc:Description</span></code>
        </td>
        <td class="mapping">

This field maps to the same `Address` objects as created for BT-727-Part, BT-5121-Part, BT-5131-Part, BT-5071-Part, BT-5101-Part and BT-5141-Part.
For each `cac:RealizedLocation`, add or update the corresponding `Address` object in the `tender.deliveryAddresses` array and map to the address's `.description`, concatenating to the existing entry in this field if necessary.

```xml
<cac:RealizedLocation>
  <cbc:Description languageID="ENG">Further realizations ...</cbc:Description>
</cac:RealizedLocation>
```

```json
{
  "tender": {
    "deliveryLocations": [
      {
        "description": "Further realizations ..."
      }
    ]
  }
}
```

</td>
      </tr>
      <tr id="BT-728-Procedure">
        <td class="field break-all">
            <p><b>BT-728-Procedure</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/procedure-lot-part-information.html#performancePlaceSection"></a><br>Place Performance Additional Information</p><p><i>BT-728:</i> Additional information about the place of performance.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProject/cac:RealizedLocation/cbc:Description</span></code>
        </td>
        <td class="mapping">

This field maps to the same `Address` objects as created for BT-727-Part, BT-5121-Part, BT-5071-Part, BT-727-Part, BT-5101-Part and BT-5141-Part.
For each `cac:RealizedLocation`, add or update the corresponding `Address` object in the `tender.deliveryAddresses` array and map to the address's `.description`, concatenating to the existing entry in this field if necessary.

```xml
<cac:RealizedLocation>
  <cbc:Description languageID="ENG">Further realizations ...</cbc:Description>
</cac:RealizedLocation>
```

```json
{
  "tender": {
    "deliveryLocations": [
      {
        "description": "Further realizations ..."
      }
    ]
  }
}
```

</td>
      </tr>
      <tr id="BT-729-Lot">
        <td class="field break-all">
            <p><b>BT-729-Lot</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/procedure-lot-part-information.html#subcontractingObligationSection"></a><br>Subcontracting Obligation Maximum</p><p><i>BT-729:</i> The maximum percentage of the contract value that the contractor must subcontract using the competitive procedure described in Title III of Directive 2009/81/EC.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='Lot']/cac:TenderingTerms/cac:AllowedSubcontractTerms/cbc:MaximumPercent</span></code>
        </td>
        <td class="mapping">

<a href="operations.md#get-the-lot-for-a-procurementprojectlot">Get the lot for the ProcurementProjectLot</a> and map to its `.subcontracting.competitiveMaximumPercentage`.

```xml
<cac:AllowedSubcontractTerms>
  <cbc:MaximumPercent>45.5</cbc:MaximumPercent>
</cac:AllowedSubcontractTerms>
```

```json
{
  "tender": {
    "lots": [
      {
        "subcontracting": {
          "competitiveMaximumPercentage": 45.5
        }
      }
    ]
  }
}
```

</td>
      </tr>
      <tr id="BT-730-Tender">
        <td class="field break-all">
            <p><b>BT-730-Tender</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/competition-results.html#lotTenderSection"></a><br>Subcontracting Value Known</p><p><i>BT-730:</i> The buyer knows at least the estimated value of the part of the contract that the contractor will subcontract to third parties.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:NoticeResult/efac:LotTender/efac:SubcontractingTerm/efbc:ValueKnownIndicator</span></code>
        </td>
        <td class="mapping">

Discard. If the award's `.subcontracting.value` is not empty, the buyer knows the estimated value of the part of the contract that the contractor will subcontract to third parties.

```xml
<efac:SubcontractingTerm>
  <efbc:ValueKnownIndicator>false</efbc:ValueKnownIndicator>
</efac:SubcontractingTerm>
```



</td>
      </tr>
      <tr id="BT-731-Tender">
        <td class="field break-all">
            <p><b>BT-731-Tender</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/competition-results.html#lotTenderSection"></a><br>Subcontracting Percentage Known</p><p><i>BT-731:</i> The buyer knows at least the estimated percentage of the contract that the contractor will subcontract to third parties compared to the whole contract.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:NoticeResult/efac:LotTender/efac:SubcontractingTerm/efbc:PercentageKnownIndicator</span></code>
        </td>
        <td class="mapping">

Discard. If the award's `.subcontracting.minimumPercentage` and `.subcontracting.maximumPercentage` are not empty, the buyer knows the estimated value of the part of the contract that the contractor will subcontract to third parties.

```xml
<efac:SubcontractingTerm>
  <efbc:PercentageKnownIndicator>true</efbc:PercentageKnownIndicator>
</efac:SubcontractingTerm>
```



</td>
      </tr>
      <tr id="BT-732-Lot">
        <td class="field break-all">
            <p><b>BT-732-Lot</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/procedure-lot-part-information.html#securityClearanceSection"></a><br>Security Clearance Description</p><p><i>BT-732:</i> Additional information about the security clearance (e.g. which level of security clearance is required, which team members must have it, whether it is necessary already for accessing the procurement documents or only for contract execution).</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='Lot']/cac:TenderingTerms/cac:SecurityClearanceTerm/cbc:Description</span></code>
        </td>
        <td class="mapping">

<a href="operations.md#get-the-lot-for-a-procurementprojectlot">Get the lot for the ProcurementProjectLot</a> and map to its `.otherRequirements.securityClearance`.

```xml
<cac:SecurityClearanceTerm>
  <cbc:Description languageID="ENG">EU Confidential security clearance of Key Management Personnel must be achieved before access to procurement documents be granted</cbc:Description>
</cac:SecurityClearanceTerm>
```

```json
{
  "tender": {
    "lots": [
      {
        "otherRequirements": {
          "securityClearance": "EU Confidential security clearance of Key Management Personnel must be achieved before access to procurement documents be granted"
        }
      }
    ]
  }
}
```

</td>
      </tr>
      <tr id="BT-733-Lot">
        <td class="field break-all">
            <p><b>BT-733-Lot</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/procedure-lot-part-information.html#awardCriteriaSection"></a><br>Award Criteria Order Justification</p><p><i>BT-733:</i> The justification for only indicating the award criteria's order of importance, not their weighing.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='Lot']/cac:TenderingTerms/cac:AwardingTerms/cac:AwardingCriterion/cbc:Description</span></code>
        </td>
        <td class="mapping">

<a href="operations.md#get-the-lot-for-a-procurementprojectlot">Get the lot for the ProcurementProjectLot</a> and map to its `.awardCriteria.orderRationale`.

```xml
<cac:AwardingCriterion>
  <cbc:Description languageID="ENG">Each criterion is evaluated separately ...</cbc:Description>
</cac:AwardingCriterion>
```

```json
{
  "tender": {
    "lots": [
      {
        "awardCriteria": {
          "orderRationale": "Each criterion is evaluated separately ..."
        }
      }
    ]
  }
}
```

</td>
      </tr>
      <tr id="BT-733-LotsGroup">
        <td class="field break-all">
            <p><b>BT-733-LotsGroup</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/procedure-lot-part-information.html#awardCriteriaSection"></a><br>Award Criteria Order Justification</p><p><i>BT-733:</i> The justification for only indicating the award criteria's order of importance, not their weighing.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='LotsGroup']/cac:TenderingTerms/cac:AwardingTerms/cac:AwardingCriterion/cbc:Description</span></code>
        </td>
        <td class="mapping">

<a href="operations.md#get-the-lot-group-for-a-procurementprojectlot">Get the lot group for the ProcurementProjectLot</a> and map to its `.awardCriteria.orderRationale`.

```xml
<cac:AwardingCriterion>
  <cbc:Description languageID="ENG">Each criterion is evaluated separately ...</cbc:Description>
</cac:AwardingCriterion>
```

```json
{
  "tender": {
    "lotGroups": [
      {
        "awardCriteria": {
          "orderRationale": "Each criterion is evaluated separately ..."
        }
      }
    ]
  }
}
```

</td>
      </tr>
      <tr id="BT-734-Lot">
        <td class="field break-all">
            <p><b>BT-734-Lot</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/procedure-lot-part-information.html#awardCriteriaSection"></a><br>Award Criterion Name</p><p><i>BT-734:</i> The name of the award criterion.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='Lot']/cac:TenderingTerms/cac:AwardingTerms/cac:AwardingCriterion/cac:SubordinateAwardingCriterion/cbc:Name</span></code>
        </td>
        <td class="mapping">

This field maps to the same `AwardCriterion` objects as created for BT-539-Lot, BT-540-Lot, BT-541-Lot, BT-5421-Lot, BT-5422-Lot and BT-5423-Lot.

<a href="operations.md#get-the-lot-for-a-procurementprojectlot">Get the lot for the ProcurementProjectLot</a>.
For each `cac:SubordinateAwardingCriterion`, add or update a corresponding `AwardCriterion` in the lot's `.awardCriteria.criteria` array and map to the the award criterion's `.name`.

```xml
<cac:SubordinateAwardingCriterion>
  <cbc:Name languageID="ENG">Technical merit</cbc:Name>
</cac:SubordinateAwardingCriterion>
```

```json
{
  "tender": {
    "lots": [
      {
        "awardCriteria": {
          "criteria": [
            {
              "name": "Technical merit"
            }
          ]
        }
      }
    ]
  }
}
```

</td>
      </tr>
      <tr id="BT-734-LotsGroup">
        <td class="field break-all">
            <p><b>BT-734-LotsGroup</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/procedure-lot-part-information.html#awardCriteriaSection"></a><br>Award Criterion Name</p><p><i>BT-734:</i> The name of the award criterion.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='LotsGroup']/cac:TenderingTerms/cac:AwardingTerms/cac:AwardingCriterion/cac:SubordinateAwardingCriterion/cbc:Name</span></code>
        </td>
        <td class="mapping">

This field maps to the same `AwardCriterion` objects as created for BT-539-LotsGroup, BT-540-LotsGroup, BT-541-LotsGroup, BT-5421-LotsGroup, BT-5422-LotsGroup and BT-5423-LotsGroup.

<a href="operations.md#get-the-lot-group-for-a-procurementprojectlot">Get the lot group for the ProcurementProjectLot</a>.
For each `cac:SubordinateAwardingCriterion`, add or update a corresponding `AwardCriterion` in the lot group's `.awardCriteria.criteria` array and map to the the award criterion's `.name`.

```xml
<cac:SubordinateAwardingCriterion>
  <cbc:Name languageID="ENG">Technical merit</cbc:Name>
</cac:SubordinateAwardingCriterion>
```

```json
{
  "tender": {
    "lotGroups": [
      {
        "awardCriteria": {
          "criteria": [
            {
              "name": "Technical merit"
            }
          ]
        }
      }
    ]
  }
}
```

</td>
      </tr>
      <tr id="BT-735-Lot">
        <td class="field break-all">
            <p><b>BT-735-Lot</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/procedure-lot-part-information.html#CVDDirectiveLotSection"></a><br>CVD Contract Type</p><p><i>BT-735:</i> The CVD legal basis to establish which category of contract types (purchase, lease, rent, hired-purchase, public service contracts and service contracts according to table 1 CVD) applies.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='Lot']/cac:TenderingTerms/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:StrategicProcurement/efac:StrategicProcurementInformation/efbc:ProcurementCategoryCode</span></code>
        </td>
        <td class="mapping">

- <a href="operations.md#get-the-lot-for-a-procurementprojectlot">Get the lot for the ProcurementProjectLot</a> and add a `Classification` object to the lot's `additionalClassifications` array.
- Set the classification's `.scheme` to 'CVDContractType'.
- Map the value of the field to the classification's `.id`.
- Look up the code's label in the <a href="https://op.europa.eu/en/web/eu-vocabularies/concept-scheme/-/resource?uri=http://publications.europa.eu/resource/authority/cvd-contract-type">authority table</a> and map it to the classification's `.description`.

```xml
<efac:StrategicProcurementInformation>
  <efbc:ProcurementCategoryCode listName="cvd-contract-type">oth-serv-contr</efbc:ProcurementCategoryCode>
</efac:StrategicProcurementInformation>
```

```json
{
  "tender": {
    "lots": [
      {
        "additionalClassifications": [
          {
            "id": "oth-serv-contr",
            "scheme": "CVDContractType",
            "description": "other service contract"
          }
        ]
      }
    ]
  }
}
```

</td>
      </tr>
      <tr id="BT-735-LotResult">
        <td class="field break-all">
            <p><b>BT-735-LotResult</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/procedure-lot-part-information.html#CVDDirectiveLotSection"></a><br>CVD Contract Type</p><p><i>BT-735:</i> The CVD legal basis to establish which category of contract types (purchase, lease, rent, hired-purchase, public service contracts and service contracts according to table 1 CVD) applies.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:NoticeResult/efac:LotResult/efac:StrategicProcurement/efac:StrategicProcurementInformation/efbc:ProcurementCategoryCode</span></code>
        </td>
        <td class="mapping">

This field maps to the same `Item` objects as created for OPT-155-LotResult and BT-723-LotResult. If no `Item` objects were created for `ancestor::efac:StrategicProcurementInformation/efbc:ProcurementDetails`:

- <a href="operations.md#get-the-award-for-a-lotresult">Get the award for the LotResult</a>.
- Add an `Item` object to its `items` array.
- Set the item's `.id` incrementally.

For each `ancestor::efac:ProcurementDetails/efac:StrategicProcurementStatistics/efbc:StatisticsCode` add a `Classification` object to the corresponding item's `additionalClassifications` array.

- Set the classification's `.scheme` to "CVDContractType".
- Map to the classification's `.id`.
- Look up the code's label in the <a href="https://op.europa.eu/en/web/eu-vocabularies/concept-scheme/-/resource?uri=http://publications.europa.eu/resource/authority/cvd-contract-type">authority table</a> and map it to the classification's `.description`.

```xml
<efac:StrategicProcurementInformation>
  <efbc:ProcurementCategoryCode listName="cvd-contract-type">oth-serv-contr</efbc:ProcurementCategoryCode>
</efac:StrategicProcurementInformation>
```

```json
{
  "awards": [
    {
      "items": [
        {
          "id": "1",
          "additionalClassifications": [
            {
              "id": "oth-serv-contr",
              "scheme": "CVDContractType",
              "description": "other service contract"
            }
          ]
        }
      ]
    }
  ]
}
```

</td>
      </tr>
      <tr id="BT-736-Lot">
        <td class="field break-all">
            <p><b>BT-736-Lot</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/procedure-lot-part-information.html#reservedExecutionSection"></a><br>Reserved Execution</p><p><i>BT-736:</i> Whether the execution of the contract must be performed in the framework of sheltered employment programmes.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='Lot']/cac:TenderingTerms/cac:ContractExecutionRequirement/cbc:ExecutionRequirementCode[@listName='reserved-execution']</span></code>
        </td>
        <td class="mapping">

If "yes", <a href="operations.md#get-the-lot-for-a-procurementprojectlot">get the lot for the ProcurementProjectLot</a> and set the lot's `.contractTerms.reservedExecution` to `true`. Otherwise, discard.

```xml
<cac:ContractExecutionRequirement>
  <cbc:ExecutionRequirementCode listName="reserved-execution">yes</cbc:ExecutionRequirementCode>
</cac:ContractExecutionRequirement>
```

```json
{
  "tender": {
    "lots": [
      {
        "contractTerms": {
          "reservedExecution": true
        }
      }
    ]
  }
}
```

</td>
      </tr>
      <tr id="BT-736-Part">
        <td class="field break-all">
            <p><b>BT-736-Part</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/procedure-lot-part-information.html#reservedExecutionSection"></a><br>Reserved Execution</p><p><i>BT-736:</i> Whether the execution of the contract must be performed in the framework of sheltered employment programmes.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='Part']/cac:TenderingTerms/cac:ContractExecutionRequirement/cbc:ExecutionRequirementCode[@listName='reserved-execution']</span></code>
        </td>
        <td class="mapping">

Set `tender.contractTerms.reservedExecution` to `true` if `@ExecutionRequirementCode` is "yes", otherwise discard.

```xml
<cac:ContractExecutionRequirement>
  <cbc:ExecutionRequirementCode listName="reserved-execution">yes</cbc:ExecutionRequirementCode>
</cac:ContractExecutionRequirement>
```

```json
{
  "tender": {
    "contractTerms": {
      "reservedExecution": true
    }
  }
}
```

</td>
      </tr>
      <tr id="BT-737-Lot">
        <td class="field break-all">
            <p><b>BT-737-Lot</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/procedure-lot-part-information.html#procurementDocsSection"></a><br>Documents Unofficial Language</p><p><i>BT-737:</i> The language(s) in which the procurement documents (or their parts) are unofficially available. These linguistic versions are not an official translation, they are provided only for information.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='Lot']/cac:TenderingTerms/cac:CallForTendersDocumentReference/cbc:LanguageID[../cbc:DocumentStatusCode/text()='non-official']</span></code>
        </td>
        <td class="mapping">

<a href="operations.md#get-the-document-for-a-document-reference">Get the document for the document reference</a>.

Set the document's `.unofficialTranslation` to `true`.

<a href="operations.md#get-the-lot-for-a-procurementprojectlot">Get the lot for the ProcurementProjectLot</a> and add its `id` to the document's `.relatedLots`.

```xml
<cac:ProcurementProjectLot>
  <cbc:ID schemeName="Lot">LOT-0001</cbc:ID>
  <cac:TenderingTerms>
    <cac:CallForTendersDocumentReference>
      <cbc:ID>20210521/CTFD/ENG/7654-02</cbc:ID>
      <cbc:DocumentStatusCode listName="document-status">non-official</cbc:DocumentStatusCode>
    </cac:CallForTendersDocumentReference>
  </cac:TenderingTerms>
</cac:ProcurementProjectLot>
```

```json
{
  "tender": {
    "documents": [
      {
        "id": "20210521/CTFD/ENG/7654-02",
        "unofficialTranslation": true,
        "relatedLots": [
          "LOT-0001"
        ]
      }
    ]
  }
}
```

</td>
      </tr>
      <tr id="BT-737-Part">
        <td class="field break-all">
            <p><b>BT-737-Part</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/procedure-lot-part-information.html#procurementDocsSection"></a><br>Documents Unofficial Language</p><p><i>BT-737:</i> The language(s) in which the procurement documents (or their parts) are unofficially available. These linguistic versions are not an official translation, they are provided only for information.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='Part']/cac:TenderingTerms/cac:CallForTendersDocumentReference/cbc:LanguageID[../cbc:DocumentStatusCode/text()='non-official']</span></code>
        </td>
        <td class="mapping">

<a href="operations.md#get-the-document-for-a-document-reference">Get the document for the document reference</a>.

Set the document's `.unofficialTranslation` to `true`.

```xml
<cac:CallForTendersDocumentReference>
  <cbc:ID>20210521/CTFD/ENG/7654-02</cbc:ID>
  <cbc:DocumentStatusCode listName="document-status">non-official</cbc:DocumentStatusCode>
</cac:CallForTendersDocumentReference>
```

```json
{
  "tender": {
    "documents": [
      {
        "id": "20210521/CTFD/ENG/7654-02",
        "unofficialTranslation": true
      }
    ]
  }
}
```

</td>
      </tr>
      <tr id="BT-738-notice">
        <td class="field break-all">
            <p><b>BT-738-notice</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/notice-information.html#preferredDateSection"></a><br>Notice Preferred Publication Date</p><p><i>BT-738:</i> The preferred date of publication of the notice on TED (e.g. to avoid publication during a national holiday). </p>
            <code class="docutils literal notranslate"><span class="pre">/*/cbc:RequestedPublicationDate</span></code>
        </td>
        <td class="mapping">

<a href="operations.md#convert-a-date-to-iso-format">Convert date to ISO format</a> and map to `tender.communication.noticeRequestedPublicationDate`.

```xml
<cbc:RequestedPublicationDate>2020-03-15+01:00</cbc:RequestedPublicationDate>
```

```json
{
  "tender": {
    "communication": {
      "noticeRequestedPublicationDate": "2020-03-15T00:00:00+01:00"
    }
  }
}
```

</td>
      </tr>
      <tr id="BT-739-Organization-Company">
        <td class="field break-all">
            <p><b>BT-739-Organization-Company</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/parties.html#_general_structure_of_an_organization_related_information"></a><br>Organisation Contact Fax</p><p><i>BT-739:</i> The fax number for contacting the organisation. To avoid unnecessary processing of personal data, the fax number shall allow the identification of a physical person only when necessary (in the sense of the Regulation (EU) 2016/679 and Regulation (EU) 2018/1725).</p>
            <code class="docutils literal notranslate"><span class="pre">/*/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:Organizations/efac:Organization/efac:Company/cac:Contact/cbc:Telefax</span></code>
        </td>
        <td class="mapping">

<a href="operations.md#get-the-organization-for-a-company">Get the organization for the company</a> and map to the organization's `.contactPoint.faxNumber`

```xml
<efac:Organization>
  <efac:Company>
    <cac:Contact>
      <cbc:Telefax>(+33) 2 34 56 78 91</cbc:Telefax>
    </cac:Contact>
  </efac:Company>
</efac:Organization>
```

```json
{
  "parties": [
    {
      "contactPoint": {
        "faxNumber": "(+33) 2 34 56 78 91"
      }
    }
  ]
}
```

</td>
      </tr>
      <tr id="BT-739-Organization-TouchPoint">
        <td class="field break-all">
            <p><b>BT-739-Organization-TouchPoint</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/parties.html#_general_structure_of_an_organization_related_information"></a><br>Contact Fax</p><p><i>BT-739:</i> The fax number for contacting the organisation. To avoid unnecessary processing of personal data, the fax number shall allow the identification of a physical person only when necessary (in the sense of the Regulation (EU) 2016/679 and Regulation (EU) 2018/1725).</p>
            <code class="docutils literal notranslate"><span class="pre">/*/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:Organizations/efac:Organization/efac:TouchPoint/cac:Contact/cbc:Telefax</span></code>
        </td>
        <td class="mapping">

<a href="operations.md#get-the-organization-for-a-touchpoint">Get the organization for the touchpoint</a> and map to the organization's `.contactPoint.faxNumber`

```xml
<efac:Organization>
  <efac:TouchPoint>
    <cac:Contact>
      <cbc:Telefax>(+33) 2 34 56 78 91</cbc:Telefax>
    </cac:Contact>
  </efac:TouchPoint>
</efac:Organization>
```

```json
{
  "parties": [
    {
      "contactPoint": {
        "faxNumber": "(+33) 2 34 56 78 91"
      }
    }
  ]
}
```

</td>
      </tr>
      <tr id="BT-739-UBO">
        <td class="field break-all">
            <p><b>BT-739-UBO</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/parties.html#ultimateBeneficialOwnerSection"></a><br>UBO Contact Fax</p><p><i>BT-739:</i> The fax number for contacting the organisation. To avoid unnecessary processing of personal data, the fax number shall allow the identification of a physical person only when necessary (in the sense of the Regulation (EU) 2016/679 and Regulation (EU) 2018/1725).</p>
            <code class="docutils literal notranslate"><span class="pre">/*/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:Organizations/efac:UltimateBeneficialOwner/cac:Contact/cbc:Telefax</span></code>
        </td>
        <td class="mapping">

<a href="operations.md#get-the-person-for-an-ultimate-beneficial-owner">Get the person for the ultimate beneficial owner</a> and map to the person's `.faxNumber`.

```xml
<efac:UltimateBeneficialOwner>
  <cac:Contact>
    <cbc:Telefax>+123 4567891</cbc:Telefax>
  </cac:Contact>
</efac:UltimateBeneficialOwner>
```

```json
{
  "parties": [
    {
      "beneficialOwners": [
        {
          "faxNumber": "+123 4567891"
        }
      ]
    }
  ]
}
```

</td>
      </tr>
      <tr id="BT-740-Procedure-Buyer">
        <td class="field break-all">
            <p><b>BT-740-Procedure-Buyer</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/parties.html#_buyer_information"></a><br>Buyer Contracting Entity</p><p><i>BT-740:</i> The buyer is a contracting entity.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ContractingParty/cac:ContractingPartyType/cbc:PartyTypeCode[@listName='buyer-contracting-type']</span></code>
        </td>
        <td class="mapping">

<a href="operations.md#get-the-organization-for-the-buyer">Get the organization for the buyer</a> and add a `Classification` object to its `.details.classifications` array.

- Map the value of this field to the classification's `.id`.
- Set its `.description` according to the <a href="codelists/buyer-contracting-type">buyer contracting type mapping table</a> and set its `.scheme` to 'buyer-contracting-type'.

```xml
<cac:ContractingPartyType>
  <cbc:PartyTypeCode listName="buyer-contracting-type">cont-ent</cbc:PartyTypeCode>
</cac:ContractingPartyType>
```

```json
{
  "parties": [
    {
      "id": "ORG-0001",
      "details": {
        "classifications": [
          {
            "scheme": "buyer-contracting-type",
            "id": "cont-ent",
            "description": "Contracting Entity"
          }
        ]
      }
    }
  ]
}
```

</td>
      </tr>
      <tr id="BT-743-Lot">
        <td class="field break-all">
            <p><b>BT-743-Lot</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/procedure-lot-part-information.html#eInvoicingSection"></a><br>Electronic Invoicing</p><p><i>BT-743:</i> Whether the buyer will require, allow or not allow electronic invoices.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='Lot']/cac:TenderingTerms/cac:ContractExecutionRequirement/cbc:ExecutionRequirementCode[@listName='einvoicing']</span></code>
        </td>
        <td class="mapping">

<a href="operations.md#get-the-lot-for-a-procurementprojectlot">Get the lot for the ProcurementProjectLot</a> and set its `.contractTerms.electronicInvoicingPolicy` according to <a href="https://extensions.open-contracting.org/en/extensions/contractTerms/master/codelists/">the allowed values</a>.

```xml
<cac:ContractExecutionRequirement>
  <cbc:ExecutionRequirementCode listName="einvoicing">required</cbc:ExecutionRequirementCode>
</cac:ContractExecutionRequirement>
```

```json
{
  "tender": {
    "lots": [
      {
        "contractTerms": {
          "electronicInvoicingPolicy": "required"
        }
      }
    ]
  }
}
```

</td>
      </tr>
      <tr id="BT-744-Lot">
        <td class="field break-all">
            <p><b>BT-744-Lot</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/procedure-lot-part-information.html#eSignatureSubmissionSection"></a><br>Submission Electronic Signature</p><p><i>BT-744:</i> Advanced or qualified electronic signature or seal (as defined in European Parliament and Council Regulation (EU) No 910/2014) is required.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='Lot']/cac:TenderingTerms/cac:ContractExecutionRequirement/cbc:ExecutionRequirementCode[@listName='esignature-submission']</span></code>
        </td>
        <td class="mapping">

<a href="operations.md#get-the-lot-for-a-procurementprojectlot">Get the lot for the ProcurementProjectLot</a> and set its `.submissionTerms.advancedElectronicSignaturePolicy` to "required".

```xml
<cac:ContractExecutionRequirement>
  <cbc:ExecutionRequirementCode listName="esignature-submission">false</cbc:ExecutionRequirementCode>
</cac:ContractExecutionRequirement>
```

```json
{
  "tender": {
    "lots": [
      {
        "submissionTerms": {
          "advancedElectronicSignaturePolicy": "required"
        }
      }
    ]
  }
}
```

</td>
      </tr>
      <tr id="BT-745-Lot">
        <td class="field break-all">
            <p><b>BT-745-Lot</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/procedure-lot-part-information.html#nonelectronicSection"></a><br>Submission Nonelectronic Description</p><p><i>BT-745:</i> The description of how to submit tenders, requests to participate, or expressions of interest non-electronically.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='Lot']/cac:TenderingProcess/cac:ProcessJustification[cbc:ProcessReasonCode/@listName='no-esubmission-justification']/cbc:Description</span></code>
        </td>
        <td class="mapping">

<a href="operations.md#get-the-lot-for-a-procurementprojectlot">Get the lot for the ProcurementProjectLot</a> and map to its `.submissionMethodDetails`.

```xml
<cac:ProcessJustification>
  <cbc:Description languageID="ENG">Tenders shall be sent per registered letter ...</cbc:Description>
</cac:ProcessJustification>
```

```json
{
  "tender": {
    "lots": [
      {
        "submissionMethodDetails": "Tenders shall be sent per registered letter ..."
      }
    ]
  }
}
```

</td>
      </tr>
      <tr id="BT-746-Organization">
        <td class="field break-all">
            <p><b>BT-746-Organization</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/parties.html#_general_structure_of_an_organization_related_information"></a><br>Winner Listed</p><p><i>BT-746:</i> The nationality (or nationalities) of the beneficiary owner(s) of the winner, tenderer, or subcontractor is not published in the register(s) established by Directive (EU) 2018/843, because the winner is listed on a regulated market (e.g. a stock exchange) that ensures adequate transparency in line with anti-money laundering legislation.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:Organizations/efac:Organization/efbc:ListedOnRegulatedMarketIndicator</span></code>
        </td>
        <td class="mapping">

<a href="operations.md#get-the-organization-for-a-company">Get the organization for the company</a> and map to the organization's `.details.listedOnRegulatedMarket`.

```xml
<efac:Organization>
  <efbc:ListedOnRegulatedMarketIndicator>false</efbc:ListedOnRegulatedMarketIndicator>
</efac:Organization>
```

```json
{
  "parties": [
    {
      "details": {
        "listedOnRegulatedMarket": "false"
      }
    }
  ]
}
```

</td>
      </tr>
      <tr id="BT-747-Lot">
        <td class="field break-all">
            <p><b>BT-747-Lot</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/procedure-lot-part-information.html#selectionCriteriaSection"></a><br>Selection Criteria Type</p><p><i>BT-747:</i> The criteria (or criterion) concern(s), for example, economic and financial standing or technical and professional ability. </p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='Lot']/cac:TenderingTerms/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:SelectionCriteria/cbc:CriterionTypeCode[@listName='selection-criterion']</span></code>
        </td>
        <td class="mapping">

If `cbc:CalculationExpressionCode[@listName="usage"]` is not set to "used", discard. Otherwise, these values are mapped to the same `SelectionCriterion` objects as created for BT-40, BT-749, BT-750, BT-752, BT-7531 and BT-7532.

- <a href="operations.md#get-the-lot-for-a-procurementprojectlot">Get the lot for the ProcurementProjectLot</a>.
- For each `<efac:SelectionCriteria>`, add or update a corresponding `SelectionCriterion` object in the lot's `.selectionCriteria.criteria`.
- Identify the equivalent code in the <a href="codelists/selection-criterion">selection criterion mapping table</a> and map to the criterion's `.type`.

```xml
<efac:SelectionCriteria>
  <cbc:CriterionTypeCode listName="selection-criterion">ef-stand</cbc:CriterionTypeCode>
</efac:SelectionCriteria>
```

```json
{
  "tender": {
    "lots": [
      {
        "selectionCriteria": {
          "criteria": [
            {
              "type": "economic"
            }
          ]
        }
      }
    ]
  }
}
```

</td>
      </tr>
      <tr id="BT-748-Lot">
        <td class="field break-all">
            <p><b>BT-748-Lot</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/procedure-lot-part-information.html#selectionCriteriaSection"></a><br>Selection Criteria Used</p><p><i>BT-748:</i> The criteria (or criterion) of the given type are (is) used, unused, or (in case of prior information notice used as a call for competition or to reduce time limits) the use is not yet known.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='Lot']/cac:TenderingTerms/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:SelectionCriteria/cbc:CalculationExpressionCode[@listName='usage']</span></code>
        </td>
        <td class="mapping">

Discard.

```xml
<efac:SelectionCriteria>
  <cbc:CalculationExpressionCode listName="usage">used</cbc:CalculationExpressionCode>
</efac:SelectionCriteria>
```



</td>
      </tr>
      <tr id="BT-749-Lot">
        <td class="field break-all">
            <p><b>BT-749-Lot</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/procedure-lot-part-information.html#selectionCriteriaSection"></a><br>Selection Criteria Name</p><p><i>BT-749:</i> The name of the selection criteria (or criterion).</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='Lot']/cac:TenderingTerms/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:SelectionCriteria/cbc:Name</span></code>
        </td>
        <td class="mapping">

If `cbc:CalculationExpressionCode[@listName="usage"]` is not set to "used", discard. Otherwise, these values are mapped to the same `SelectionCriterion` objects as created for BT-40-Lot, BT-747-Lot, BT-749-Lot, BT-750-Lot, BT-752-Lot, BT-7531-Lot and BT-7532-Lot.

- <a href="operations.md#get-the-lot-for-a-procurementprojectlot">Get the lot for the ProcurementProjectLot</a>.
- For each `efac:SelectionCriteria`, add or update a corresponding `SelectionCriterion` object in the lot's `.selectionCriteria.criteria`.
- Map to the criterion's `.description`. Concatenate it with <a href="#BT-750-Lot">BT-750-Lot Selection Criteria Description</a>.

```xml
<efac:SelectionCriteria>
  <cbc:Name languageID="ENG">Minimum Turnover</cbc:Name>
</efac:SelectionCriteria>
```

```json
{
  "tender": {
    "lots": [
      {
        "selectionCriteria": {
          "criteria": [
            {
              "description": "Minimum Turnover"
            }
          ]
        }
      }
    ]
  }
}
```

</td>
      </tr>
      <tr id="BT-75-Lot">
        <td class="field break-all">
            <p><b>BT-75-Lot</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/procedure-lot-part-information.html#financialGuaranteeSection"></a><br>Guarantee Required Description</p><p><i>BT-75:</i> The description of the financial guarantee required from the tenderer when submitting a tender. The guarantee can take the form of, for example, a payment to the buyer or a document from a bank. Typically, the guarantee would be forfeit when a tenderer has won the contract but then refused to sign it.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='Lot']/cac:TenderingTerms/cac:RequiredFinancialGuarantee/cbc:Description</span></code>
        </td>
        <td class="mapping">

<a href="operations.md#get-the-lot-for-a-procurementprojectlot">Get the lot for the ProcurementProjectLot</a> and map to its `.submissionTerms.depositsGuarantees`.

```xml
<cac:RequiredFinancialGuarantee>
  <cbc:Description languageID="ENG">Bids shall include a bid security (Provisional Bank Guarantee or bid bond), ...</cbc:Description>
</cac:RequiredFinancialGuarantee>
```

```json
{
  "tender": {
    "lots": [
      {
        "submissionTerms": {
          "depositsGuarantees": "Bids shall include a bid security (Provisional Bank Guarantee or bid bond), ..."
        }
      }
    ]
  }
}
```

</td>
      </tr>
      <tr id="BT-750-Lot">
        <td class="field break-all">
            <p><b>BT-750-Lot</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/procedure-lot-part-information.html#selectionCriteriaSection"></a><br>Selection Criteria Description</p><p><i>BT-750:</i> The brief description of the selection criteria (or criterion), including minimum requirements, required information (e.g. self-declaration, documentation) and how the criteria or criterion will be used to select candidates to be invited for the second stage of the procedure (if a maximum number of candidates was set).</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='Lot']/cac:TenderingTerms/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:SelectionCriteria/cbc:Description</span></code>
        </td>
        <td class="mapping">

If `cbc:CalculationExpressionCode[@listName="usage"]` is not set to "used", discard. Otherwise, these values are mapped to the same `SelectionCriterion` objects as created for BT-40-Lot, BT-747-Lot, BT-749-Lot, BT-752-Lot, BT-7531-Lot and BT-7532-Lot.

- <a href="operations.md#get-the-lot-for-a-procurementprojectlot">Get the lot for the ProcurementProjectLot</a>.
- For each `efac:SelectionCriteria`, add or update a corresponding `SelectionCriterion` object in the lot's `.selectionCriteria.criteria`.
- Map to the criterion's `.description`. Concatenate it with <a href="#BT-749-Lot">BT-749-Lot Selection Criteria Name</a>.

```xml
<efac:SelectionCriteria>
  <cbc:Description languageID="ENG">Turnover over contract value rate</cbc:Description>
</efac:SelectionCriteria>
```

```json
{
  "tender": {
    "lots": [
      {
        "selectionCriteria": {
          "criteria": [
            {
              "description": "Turnover over contract value rate"
            }
          ]
        }
      }
    ]
  }
}
```

</td>
      </tr>
      <tr id="BT-751-Lot">
        <td class="field break-all">
            <p><b>BT-751-Lot</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/procedure-lot-part-information.html#financialGuaranteeSection"></a><br>Guarantee Required</p><p><i>BT-751:</i> A guarantee is required.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='Lot']/cac:TenderingTerms/cac:RequiredFinancialGuarantee/cbc:GuaranteeTypeCode[@listName='tender-guarantee-required']</span></code>
        </td>
        <td class="mapping">

Discard. If the lot's `.submissionTerms.depositsGuarantees` is not empty, a guarantee is required.

```xml
<cac:RequiredFinancialGuarantee>
  <cbc:GuaranteeTypeCode listName="tender-guarantee-required">true</cbc:GuaranteeTypeCode>
</cac:RequiredFinancialGuarantee>
```



</td>
      </tr>
      <tr id="BT-752-Lot">
        <td class="field break-all">
            <p><b>BT-752-Lot</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/procedure-lot-part-information.html#selectionCriteriaSection"></a><br>Selection Criteria Second Stage Invite Number</p><p><i>BT-752:</i> A number linked to the selection criteria (or criterion).</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='Lot']/cac:TenderingTerms/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:SelectionCriteria/efac:CriterionParameter/efbc:ParameterNumeric</span></code>
        </td>
        <td class="mapping">

If `ancestor::efac:SelectionCriteria/cbc:CalculationExpressionCode[@listName="usage"]` is not set to "used", discard. Otherwise, these values are mapped to the same `SelectionCriterion` objects as created for BT-40-Lot, BT-747-Lot, BT-749-Lot, BT-750-Lot, BT-7531-Lot and BT-7532-Lot, and the same `SelectionCriterionNumber` objects as created for BT-7531-Lot and BT-7532-Lot.

- <a href="operations.md#get-the-lot-for-a-procurementprojectlot">Get the lot for the ProcurementProjectLot</a>.
- For each `efac:SelectionCriteria`, add or update a corresponding `SelectionCriterion` object in the lot's `.selectionCriteria.criteria`.
- For each `efac:CriterionParameter`, add or update a corresponding `SelectionCriterionNumber` object in the criterion's `.numbers`.
- Map to the number's `.number`.

```xml
<efac:CriterionParameter>
  <efbc:ParameterNumeric>2</efbc:ParameterNumeric>
</efac:CriterionParameter>
```

```json
{
  "tender": {
    "lots": [
      {
        "selectionCriteria": {
          "criteria": [
            {
              "numbers": [
                {
                  "number": 2
                }
              ]
            }
          ]
        }
      }
    ]
  }
}
```

</td>
      </tr>
      <tr id="BT-7531-Lot">
        <td class="field break-all">
            <p><b>BT-7531-Lot</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/procedure-lot-part-information.html#selectionCriteriaSection"></a><br>Selection Criteria Second Stage Invite Number Weight</p><p><i>BT-7531:</i> Whether the number linked to a selection criterion (or selection criteria) is a type of weight (e.g. a percentage).</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='Lot']/cac:TenderingTerms/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:SelectionCriteria/efac:CriterionParameter/efbc:ParameterCode[@listName='number-weight']</span></code>
        </td>
        <td class="mapping">

If `ancestor::efac:SelectionCriteria/cbc:CalculationExpressionCode[@listName="usage"]` is not set to "used", discard. Otherwise, these values are mapped to the same `SelectionCriterion` objects as created for BT-40-Lot, BT-747-Lot, BT-749-Lot, BT-750-Lot, BT-752-Lot and BT-7532-Lot, and the same `SelectionCriterionNumber` objects as created for BT-752-Lot and BT-7532-Lot.

- <a href="operations.md#get-the-lot-for-a-procurementprojectlot">Get the lot for the ProcurementProjectLot</a>.
- For each `efac:SelectionCriteria`, add or update a corresponding `SelectionCriterion` object in the lot's `.selectionCriteria.criteria`.
- For each `efac:CriterionParameter`, add or update a corresponding `SelectionCriterionNumber` object in the criterion's `.numbers`.
- Identify the equivalent code in the <a href="https://extensions.open-contracting.org/en/extensions/awardCriteria/master/codelists/#criterionWeight.csv">criterionWeight</a> codelist and map to the number's `.weight`.

```xml
<efac:CriterionParameter>
  <efbc:ParameterCode listName="number-weight">per-exa</efbc:ParameterCode>
</efac:CriterionParameter>
```

```json
{
  "tender": {
    "lots": [
      {
        "selectionCriteria": {
          "criteria": [
            {
              "numbers": [
                {
                  "weight": "percentageExact"
                }
              ]
            }
          ]
        }
      }
    ]
  }
}
```

</td>
      </tr>
      <tr id="BT-7532-Lot">
        <td class="field break-all">
            <p><b>BT-7532-Lot</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/procedure-lot-part-information.html#selectionCriteriaSection"></a><br>Selection Criteria Second Stage Invite Number Threshold</p><p><i>BT-7532:</i> Whether the number linked to a selection criterion (or selection criteria) is a type of threshold (e.g. a minimum score, a maximum number of tenders with the highest score passing).</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='Lot']/cac:TenderingTerms/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:SelectionCriteria/efac:CriterionParameter/efbc:ParameterCode[@listName='number-threshold']</span></code>
        </td>
        <td class="mapping">

If `ancestor::efac:SelectionCriteria/cbc:CalculationExpressionCode[@listName="usage"]` is not set to "used", discard. Otherwise, these values are mapped to the same `SelectionCriterion` objects as created for BT-40-Lot, BT-747-Lot, BT-749-Lot, BT-750-Lot, BT-752-Lot and BT-7531-Lot, and the same `SelectionCriterionNumber` objects as created for BT-752-Lot and BT-7531-Lot.

- <a href="operations.md#get-the-lot-for-a-procurementprojectlot">Get the lot for the ProcurementProjectLot</a>.
- For each `efac:SelectionCriteria`, add or update a corresponding `SelectionCriterion` object in the lot's `.selectionCriteria.criteria`.
- For each `efac:CriterionParameter`, add or update a corresponding `SelectionCriterionNumber` object in the criterion's `.numbers`.
- Identify the equivalent code in the <a href="https://extensions.open-contracting.org/en/extensions/awardCriteria/master/codelists/#criterionThreshold.csv">criterionThreshold</a> codelist and map to the number's `.threshold`.

```xml
<efac:CriterionParameter>
  <efbc:ParameterCode listName="number-threshold">min-score</efbc:ParameterCode>
</efac:CriterionParameter>
```

```json
{
  "tender": {
    "lots": [
      {
        "selectionCriteria": {
          "criteria": [
            {
              "numbers": [
                {
                  "threshold": "minimumScore"
                }
              ]
            }
          ]
        }
      }
    ]
  }
}
```

</td>
      </tr>
      <tr id="BT-754-Lot">
        <td class="field break-all">
            <p><b>BT-754-Lot</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/procedure-lot-part-information.html#accessibilitySection"></a><br>Accessibility</p><p><i>BT-754:</i> The use of accessibility criteria for persons with disabilities in the technical specifications.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='Lot']/cac:ProcurementProject/cac:ProcurementAdditionalType[cbc:ProcurementTypeCode/@listName='accessibility']/cbc:ProcurementTypeCode[@listName='accessibility']</span></code>
        </td>
        <td class="mapping">

<a href="operations.md#get-the-lot-for-a-procurementprojectlot">Get the lot for the ProcurementProjectLot</a>. If "inc", set the lot's `.hasAccessibilityCriteria` to "true", otherwise set to "false". If "n-inc", set the lot's `.noAccessibilityCriteriaRationale` to "Procurement is not intended for use by natural persons".

```xml
<cac:ProcurementAdditionalType>
  <cbc:ProcurementTypeCode listName="accessibility">n-inc-just</cbc:ProcurementTypeCode>
</cac:ProcurementAdditionalType>
```

```json
{
  "tender": {
    "lots": [
      {
        "hasAccessibilityCriteria": "false"
      }
    ]
  }
}
```

</td>
      </tr>
      <tr id="BT-755-Lot">
        <td class="field break-all">
            <p><b>BT-755-Lot</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/procedure-lot-part-information.html#accessibilitySection"></a><br>Accessibility Justification</p><p><i>BT-755:</i> The justification for not including accessibility criteria even though the procurement is intended for use by natural persons.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='Lot']/cac:ProcurementProject/cac:ProcurementAdditionalType[cbc:ProcurementTypeCode/@listName='accessibility']/cbc:ProcurementType</span></code>
        </td>
        <td class="mapping">

<a href="operations.md#get-the-lot-for-a-procurementprojectlot">Get the lot for the ProcurementProjectLot</a> and map to the lot's `.noAccessibilityCriteriaRationale`.

```xml
<cac:ProcurementAdditionalType>
  <cbc:ProcurementType languageID="ENG">Accessibility criteria are not included ...</cbc:ProcurementType>
</cac:ProcurementAdditionalType>
```

```json
{
  "tender": {
    "lots": [
      {
        "noAccessibilityCriteriaRationale": "Accessibility criteria are not included ..."
      }
    ]
  }
}
```

</td>
      </tr>
      <tr id="BT-756-Procedure">
        <td class="field break-all">
            <p><b>BT-756-Procedure</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/procedure-lot-part-information.html#competitionTerminationSection"></a><br>PIN Competition Termination</p><p><i>BT-756:</i> The prior information notice used as a call for competition (or a specific lot) is terminated. No further contracts, besides those published in this notice, will be awarded following this prior information notice used as a call for competition. This field can be used even if no contracts are awarded in the contract award notice.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:TenderingProcess/cbc:TerminatedIndicator</span></code>
        </td>
        <td class="mapping">

If "true", set `tender.status` to 'complete'. Otherwise, discard.

```xml
<cbc:TerminatedIndicator>true</cbc:TerminatedIndicator>
```

```json
{
  "tender": {
    "status": "complete"
  }
}
```

</td>
      </tr>
      <tr id="BT-757-notice">
        <td class="field break-all">
            <p><b>BT-757-notice</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/notice-information.html#noticeIDSection"></a><br>Notice Version</p><p><i>BT-757:</i> The version of the notice. This helps, for example, to keep track of versions of notices or changes to notices before publication.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cbc:VersionID</span></code>
        </td>
        <td class="mapping">

Discard.

```xml
<cbc:VersionID>01</cbc:VersionID>
```



</td>
      </tr>
      <tr id="BT-758-notice">
        <td class="field break-all">
            <p><b>BT-758-notice</b> <br>Change Notice Version Identifier</p><p><i>BT-758:</i> The reference to the version of the previous notice that should be changed. This helps, for example, to keep track of versions of notices or changes to notices before publication.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:Changes/efbc:ChangedNoticeIdentifier</span></code>
        </td>
        <td class="mapping">

Discard.

```xml
<efac:Changes>
  <efbc:ChangedNoticeIdentifier schemeName="notice-id-ref">755db7f6-6aa1-453b-9087-1df5f7725112-02</efbc:ChangedNoticeIdentifier>
</efac:Changes>
```



</td>
      </tr>
      <tr id="BT-759-LotResult">
        <td class="field break-all">
            <p><b>BT-759-LotResult</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/competition-results.html#_lot_result"></a><br>Received Submissions Count</p><p><i>BT-759:</i> Number of tenders or requests to participate received. Tenders including variants or multiple tenders submitted (for one lot) by the same tenderer should be counted as one tender.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:NoticeResult/efac:LotResult/efac:ReceivedSubmissionsStatistics/efbc:StatisticsNumeric</span></code>
        </td>
        <td class="mapping">

This field maps to the same `Statistic` objects as created for BT-760-LotResult.

For each `efac:ReceivedSubmissionsStatistics`, <a href="operations.md#add-a-statistic">add a bids statistic</a> or update the corresponding `Statistic` object and map to its `.value`.

<a href="operations.md#get-the-lot-for-a-lotresult">Get the lot for the LotResult</a> and add the lot's `.id` to the statistic's `.relatedLots`.

```xml
<efac:ReceivedSubmissionsStatistics>
  <efbc:StatisticsNumeric>12</efbc:StatisticsNumeric>
</efac:ReceivedSubmissionsStatistics>
```

```json
{
  "bids": {
    "statistics": [
      {
        "value": 12
      }
    ]
  }
}
```

</td>
      </tr>
      <tr id="BT-76-Lot">
        <td class="field break-all">
            <p><b>BT-76-Lot</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/procedure-lot-part-information.html#tendererReqsSection"></a><br>Tenderer Legal Form Description</p><p><i>BT-76:</i> The legal form that must be taken by a group of tenderers that is awarded a contract.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='Lot']/cac:TenderingTerms/cac:TendererQualificationRequest[not(cac:SpecificTendererRequirement)]/cbc:CompanyLegalForm</span></code>
        </td>
        <td class="mapping">

<a href="operations.md#get-the-lot-for-a-procurementprojectlot">Get the lot for the ProcurementProjectLot</a> and map to its `.contractTerms.tendererLegalForm`.

```xml
<cac:TendererQualificationRequest>
  <cbc:CompanyLegalForm languageID="ENG">The tenderer ...</cbc:CompanyLegalForm>
</cac:TendererQualificationRequest>
```

```json
{
  "tender": {
    "lots": [
      {
        "contractTerms": {
          "tendererLegalForm": "The tenderer..."
        }
      }
    ]
  }
}
```

</td>
      </tr>
      <tr id="BT-760-LotResult">
        <td class="field break-all">
            <p><b>BT-760-LotResult</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/competition-results.html#_lot_result"></a><br>Received Submissions Type</p><p><i>BT-760:</i> The type of tenders or requests to participate received. The total number of tenders received shall be given. When a notice does not fall under Directive 2009/81/EC and is not about social or other specific services, the number of tenders received from micro, small and medium enterprises; the number of tenders received from tenderers registered in other European Economic Area countries and the number of tenders received from tenderers registered in countries outside of the European Economic Area shall also be given. All tenders shall be counted, regardless of whether they are admissible or inadmissible. For tenders submitted by a group of tenderers (e.g. a consortium), the tender shall be counted in the relevant category (e.g. SME) if the majority of the work is expected to be done by tenderers which fall within this category (e.g. they are SMEs).</p>
            <code class="docutils literal notranslate"><span class="pre">/*/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:NoticeResult/efac:LotResult/efac:ReceivedSubmissionsStatistics/efbc:StatisticsCode</span></code>
        </td>
        <td class="mapping">

This field maps to the same `Statistic` objects as created for BT-759-LotResult.

For each `efac:ReceivedSubmissionsStatistics`, <a href="operations.md#add-a-statistic">add a bids statistic</a> or update the corresponding `Statistic` object and map to its `.measure` according to the <a href="codelists/received-submission-type">received submission type mapping table</a>.

<a href="operations.md#get-the-lot-for-a-lotresult">Get the lot for the LotResult</a> and add the lot's `.id` to the statistic's `.relatedLots`.

```xml
<efac:ReceivedSubmissionsStatistics>
  <efbc:StatisticsCode listName="received-submission-type">t-sme</efbc:StatisticsCode>
</efac:ReceivedSubmissionsStatistics>
```

```json
{
  "bids": {
    "statistics": [
      {
        "measure": "smeBids"
      }
    ]
  }
}
```

</td>
      </tr>
      <tr id="BT-761-Lot">
        <td class="field break-all">
            <p><b>BT-761-Lot</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/procedure-lot-part-information.html#tendererReqsSection"></a><br>Tenderer Legal Form</p><p><i>BT-761:</i> A certain legal form must be taken by a group of tenderers that is awarded a contract.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='Lot']/cac:TenderingTerms/cac:TendererQualificationRequest[not(cac:SpecificTendererRequirement)]/cbc:CompanyLegalFormCode</span></code>
        </td>
        <td class="mapping">

Discard. If the lot's `.contractTerms.tendererLegalForm` is not empty, tenderers must take a certain legal form.

```xml
<cac:TendererQualificationRequest>
  <cbc:CompanyLegalForm languageID="ENG">The tenderer ...</cbc:CompanyLegalForm>
</cac:TendererQualificationRequest>
```



</td>
      </tr>
      <tr id="BT-762-notice">
        <td class="field break-all">
            <p><b>BT-762-notice</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/change-notice.html#changeReasonSection"></a><br>Change Reason Description</p><p><i>BT-762:</i> The description of the main reason for the change in the notice compared to the original notice.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:Changes/efac:ChangeReason/efbc:ReasonDescription</span></code>
        </td>
        <td class="mapping">

These values map to the same `Amendment` objects as created for BT-140. Update the corresponding `Amendment` objects and map to its `.rationale`.

```xml
<efac:ChangeReason>
  <efbc:ReasonDescription languageID="ENG">Clerical corrections of ...</efbc:ReasonDescription>
</efac:ChangeReason>
```

```json
{
  "tender": {
    "amendments": [
      {
        "rationale": "Clerical corrections of ..."
      }
    ]
  }
}
```

</td>
      </tr>
      <tr id="BT-763-Procedure">
        <td class="field break-all">
            <p><b>BT-763-Procedure</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/procedure-lot-part-information.html#allLotsSection"></a><br>Lots All Required</p><p><i>BT-763:</i> The tenderer must submit tenders for all lots.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:TenderingProcess/cbc:PartPresentationCode</span></code>
        </td>
        <td class="mapping">

Set `tender.lotDetails.maximumLotsBidPerSupplier` to the number (not the string) 1e9999 (which parses to infinity i.e. "all")

```xml
<cbc:PartPresentationCode listName="tenderlot-presentation">all</cbc:PartPresentationCode>
```

```json
{
  "tender": {
    "lotDetails": {
      "maximumLotsBidPerSupplier": 1e9999
    }
  }
}
```

</td>
      </tr>
      <tr id="BT-764-Lot">
        <td class="field break-all">
            <p><b>BT-764-Lot</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/procedure-lot-part-information.html#eCatalogueSubmissionSection"></a><br>Submission Electronic Catalogue</p><p><i>BT-764:</i> Whether it is required, allowed or not allowed to submit (parts of) tenders as electronic catalogues.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='Lot']/cac:TenderingTerms/cac:ContractExecutionRequirement/cbc:ExecutionRequirementCode[@listName='ecatalog-submission']</span></code>
        </td>
        <td class="mapping">

<a href="operations.md#get-the-lot-for-a-procurementprojectlot">Get the lot for the ProcurementProjectLot</a> and set its `.submissionTerms.electronicCataloguePolicy` according to <a href="https://extensions.open-contracting.org/en/extensions/submissionTerms/master/codelists/">the allowed values</a>.

```xml
<cac:ContractExecutionRequirement>
  <cbc:ExecutionRequirementCode listName="ecatalog-submission">allowed</cbc:ExecutionRequirementCode>
</cac:ContractExecutionRequirement>
```

```json
{
  "tender": {
    "lots": [
      {
        "submissionTerms": {
          "electronicCataloguePolicy": "allowed"
        }
      }
    ]
  }
}
```

</td>
      </tr>
      <tr id="BT-765-Lot">
        <td class="field break-all">
            <p><b>BT-765-Lot</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/procedure-lot-part-information.html#frameworkAgreementSection"></a><br>Framework Agreement</p><p><i>BT-765:</i> Whether a framework agreement with, without, or with and without the reopening of competition is involved.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='Lot']/cac:TenderingProcess/cac:ContractingSystem/cbc:ContractingSystemTypeCode[@listName='framework-agreement']</span></code>
        </td>
        <td class="mapping">

If different from 'none', <a href="operations.md#get-the-lot-for-a-procurementprojectlot">get the lot for the ProcurementProjectLot</a> and set its `.techniques.hasFrameworkAgreement` to `true`. Map the code according to the <a href="codelists/framework-agreement-method">framework agreement method mapping table</a> to the lot's `.techniques.method`. Otherwise discard.

```xml
<cac:ContractingSystem>
  <cbc:ContractingSystemTypeCode listName="framework-agreement">fa-wo-rc</cbc:ContractingSystemTypeCode>
</cac:ContractingSystem>
```

```json
{
  "tender": {
    "lots": [
      {
        "techniques": {
          "hasFrameworkAgreement": true,
          "method": "withoutReopeningCompetition"
        }
      }
    ]
  }
}
```

</td>
      </tr>
      <tr id="BT-765-Part">
        <td class="field break-all">
            <p><b>BT-765-Part</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/procedure-lot-part-information.html#frameworkAgreementSection"></a><br>Framework Agreement</p><p><i>BT-765:</i> Whether a framework agreement with, without, or with and without the reopening of competition is involved.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='Part']/cac:TenderingProcess/cac:ContractingSystem/cbc:ContractingSystemTypeCode[@listName='framework-agreement']</span></code>
        </td>
        <td class="mapping">

If different from 'none', set `tender.techniques.hasFrameworkAgreement` to `true`. Map the code according to the <a href="codelists/framework-agreement-method">framework agreement method mapping table</a> to `tender.techniques.method`. Otherwise discard.

```xml
<cac:ContractingSystem>
  <cbc:ContractingSystemTypeCode listName="framework-agreement">fa-wo-rc</cbc:ContractingSystemTypeCode>
</cac:ContractingSystem>
```

```json
{
  "tender": {
    "techniques": {
      "hasFrameworkAgreement": true,
      "method": "withoutReopeningCompetition"
    }
  }
}
```

</td>
      </tr>
      <tr id="BT-766-Lot">
        <td class="field break-all">
            <p><b>BT-766-Lot</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/procedure-lot-part-information.html#DPSSection"></a><br>Dynamic Purchasing System</p><p><i>BT-766:</i> Whether a dynamic purchasing system is involved and, in case of central purchasing bodies, whether it may be used by buyers not listed in this notice.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='Lot']/cac:TenderingProcess/cac:ContractingSystem/cbc:ContractingSystemTypeCode[@listName='dps-usage']</span></code>
        </td>
        <td class="mapping">

If different from 'none', <a href="operations.md#get-the-lot-for-a-procurementprojectlot">get the lot for the ProcurementProjectLot</a> and set its `.techniques.hasDynamicPurchasingSystem` to `true`. Map the code according to the <a href="codelists/dps-usage">DPS usage mapping table</a> to the lot's `.techniques.dynamicPurchasingSystem.type`. Otherwise discard.

```xml
<cac:ContractingSystem>
  <cbc:ContractingSystemTypeCode listName="dps-usage">dps-nlist</cbc:ContractingSystemTypeCode>
</cac:ContractingSystem>
```

```json
{
  "tender": {
    "lots": [
      {
        "techniques": {
          "hasDynamicPurchasingSystem": true,
          "dynamicPurchasingSystem": {
            "type": "closed"
          }
        }
      }
    ]
  }
}
```

</td>
      </tr>
      <tr id="BT-766-Part">
        <td class="field break-all">
            <p><b>BT-766-Part</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/procedure-lot-part-information.html#DPSSection"></a><br>Dynamic Purchasing System</p><p><i>BT-766:</i> Whether a dynamic purchasing system is involved and, in case of central purchasing bodies, whether it may be used by buyers not listed in this notice.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='Part']/cac:TenderingProcess/cac:ContractingSystem/cbc:ContractingSystemTypeCode[@listName='dps-usage']</span></code>
        </td>
        <td class="mapping">

If different from 'none', set `tender.techniques.hasDynamicPurchasingSystem` to `true`. Map the code according to the <a href="codelists/dps-usage">DPS usage mapping table</a> to `tender.techniques.dynamicPurchasingSystem.type`. Otherwise discard.

```xml
<cac:ContractingSystem>
  <cbc:ContractingSystemTypeCode listName="dps-usage">dps-nlist</cbc:ContractingSystemTypeCode>
</cac:ContractingSystem>
```

```json
{
  "tender": {
    "techniques": {
      "hasDynamicPurchasingSystem": true,
      "dynamicPurchasingSystem": {
        "type": "closed"
      }
    }
  }
}
```

</td>
      </tr>
      <tr id="BT-767-Lot">
        <td class="field break-all">
            <p><b>BT-767-Lot</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/procedure-lot-part-information.html#auctionTermsSection"></a><br>Electronic Auction</p><p><i>BT-767:</i> An electronic auction is used.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='Lot']/cac:TenderingProcess/cac:AuctionTerms/cbc:AuctionConstraintIndicator</span></code>
        </td>
        <td class="mapping">

If "true", <a href="operations.md#get-the-lot-for-a-procurementprojectlot">get the lot for the ProcurementProjectLot</a> and set the lot's `.techniques.hasElectronicAuction` to `true`. Otherwise, discard.

```xml
<cac:AuctionTerms>
  <cbc:AuctionConstraintIndicator>true</cbc:AuctionConstraintIndicator>
</cac:AuctionTerms>
```

```json
{
  "tender": {
    "lots": [
      {
        "techniques": {
          "hasElectronicAuction": true
        }
      }
    ]
  }
}
```

</td>
      </tr>
      <tr id="BT-768-Contract">
        <td class="field break-all">
            <p><b>BT-768-Contract</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/competition-results.html#settledContractSection"></a><br>Contract Framework Agreement</p><p><i>BT-768:</i> The contract is awarded within a framework agreement.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:NoticeResult/efac:SettledContract/efbc:ContractFrameworkIndicator</span></code>
        </td>
        <td class="mapping">

Discard. The contract is awarded within a framework agreement if the related lot's or tender's `.techniques.hasFrameworkAgreement` is `true`.

```xml
<efac:SettledContract>
  <efbc:ContractFrameworkIndicator>true</efbc:ContractFrameworkIndicator>
</efac:SettledContract>
```



</td>
      </tr>
      <tr id="BT-769-Lot">
        <td class="field break-all">
            <p><b>BT-769-Lot</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/procedure-lot-part-information.html#multipleTendersSection"></a><br>Multiple Tenders</p><p><i>BT-769:</i> Tenderers may submit more than one tender (for a given lot).</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='Lot']/cac:TenderingTerms/cbc:MultipleTendersCode</span></code>
        </td>
        <td class="mapping">

<a href="operations.md#get-the-lot-for-a-procurementprojectlot">Get the lot for the ProcurementProjectLot</a> and set the lot's `.submissionTerms.multipleTendersPolicy` according to <a href="https://extensions.open-contracting.org/en/extensions/submissionTerms/master/codelists/">the allowed values</a>.

```xml
<cbc:MultipleTendersCode listName="permission">allowed</cbc:MultipleTendersCode>
```

```json
{
  "tender": {
    "lots": [
      {
        "submissionTerms": {
          "multipleTendersPolicy": "allowed"
        }
      }
    ]
  }
}
```

</td>
      </tr>
      <tr id="BT-77-Lot">
        <td class="field break-all">
            <p><b>BT-77-Lot</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/procedure-lot-part-information.html#termsFinancialSection"></a><br>Terms Financial</p><p><i>BT-77:</i> The main information about financing and payment and/or reference to any provisions that govern them.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='Lot']/cac:TenderingTerms/cac:PaymentTerms/cbc:Note</span></code>
        </td>
        <td class="mapping">

<a href="operations.md#get-the-lot-for-a-procurementprojectlot">Get the lot for the ProcurementProjectLot</a> and map to its `.contractTerms.financialTerms`.

```xml
<cac:PaymentTerms>
  <cbc:Note languageID="ENG">Any payment ...</cbc:Note>
</cac:PaymentTerms>
```

```json
{
  "tender": {
    "lots": [
      {
        "contractTerms": {
          "financialTerms": "Any payment ..."
        }
      }
    ]
  }
}
```

</td>
      </tr>
      <tr id="BT-771-Lot">
        <td class="field break-all">
            <p><b>BT-771-Lot</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/procedure-lot-part-information.html#tendererReqsSection"></a><br>Late Tenderer Information</p><p><i>BT-771:</i> Whether tenderer-related information can be supplemented even after the submission deadline.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='Lot']/cac:TenderingTerms/cac:TendererQualificationRequest[not(cbc:CompanyLegalFormCode)]/cac:SpecificTendererRequirement[not(cbc:TendererRequirementTypeCode[@listName='reserved-procurement'])]/cbc:TendererRequirementTypeCode[@listName='missing-info-submission']</span></code>
        </td>
        <td class="mapping">

- <a href="operations.md#get-the-lot-for-a-procurementprojectlot">Get the lot for the ProcurementProjectLot</a>.
- Look up the code's label in the <a href="https://op.europa.eu/en/web/eu-vocabularies/concept-scheme/-/resource?uri=http://publications.europa.eu/resource/authority/missing-info-submission">authority table</a> and map it to the lot's `.submissionMethodDetails`. Append if other information is already mapped to this field.

```xml
<cac:SpecificTendererRequirement>
  <cbc:TendererRequirementTypeCode listName="missing-info-submission">late-all</cbc:TendererRequirementTypeCode>
</cac:SpecificTendererRequirement>
```

```json
{
  "tender": {
    "lots": [
      {
        "submissionMethodDetails": "All missing tenderer-related documents can be submitted later."
      }
    ]
  }
}
```

</td>
      </tr>
      <tr id="BT-772-Lot">
        <td class="field break-all">
            <p><b>BT-772-Lot</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/procedure-lot-part-information.html#tendererReqsSection"></a><br>Late Tenderer Information Description</p><p><i>BT-772:</i> Description of the tenderer-related information that can be supplemented even after the submission deadline.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='Lot']/cac:TenderingTerms/cac:TendererQualificationRequest[not(cbc:CompanyLegalFormCode)]/cac:SpecificTendererRequirement[not(cbc:TendererRequirementTypeCode[@listName='reserved-procurement'])]/cbc:Description</span></code>
        </td>
        <td class="mapping">

<a href="operations.md#get-the-lot-for-a-procurementprojectlot">Get the lot for the ProcurementProjectLot</a> and map to its `.submissionMethodDetails`. Append if other information is already mapped to this field.

```xml
<cac:SpecificTendererRequirement>
  <cbc:Description languageID="ENG">Economic operators who ...</cbc:Description>
</cac:SpecificTendererRequirement>
```

```json
{
  "tender": {
    "lots": [
      {
        "submissionMethodDetails": "Economic operators who ..."
      }
    ]
  }
}
```

</td>
      </tr>
      <tr id="BT-773-Tender">
        <td class="field break-all">
            <p><b>BT-773-Tender</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/competition-results.html#lotTenderSection"></a><br>Subcontracting</p><p><i>BT-773:</i> Whether at least a part of the contract will be subcontracted.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:NoticeResult/efac:LotTender/efac:SubcontractingTerm[efbc:TermCode/@listName='applicability']/efbc:TermCode</span></code>
        </td>
        <td class="mapping">

<a href="operations.md#get-the-bid-for-a-lottender">Get the bid for the LotTender</a>. If "yes", set the bid's `.hasSubcontracting` to `true`. If "no", set the bid's `.hasSubcontracting` to `false`.

```xml
<efac:SubcontractingTerm>
  <efbc:TermCode listName="applicability">yes</efbc:TermCode>
</efac:SubcontractingTerm>
```

```json
{
  "bids": {
    "details": [
      {
        "hasSubcontracting": true
      }
    ]
  }
}
```

</td>
      </tr>
      <tr id="BT-774-Lot">
        <td class="field break-all">
            <p><b>BT-774-Lot</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/procedure-lot-part-information.html#strategicProcurementSection"></a><br>Green Procurement</p><p><i>BT-774:</i> A process to procure goods, services and works with reduced environmental impact throughout their life cycle.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='Lot']/cac:ProcurementProject/cac:ProcurementAdditionalType/cbc:ProcurementTypeCode[@listName='environmental-impact']</span></code>
        </td>
        <td class="mapping">

<a href="operations.md#get-the-lot-for-a-procurementprojectlot">Get the lot for the ProcurementProjectLot</a> and set the lot''s `.hasSustainability` to "true".

For each `cac:ProcurementAdditionalType` add a corresponding `.sustainability` object to the lot''s `.sustainability` array.

- Map the code to the sustainability''s `.goal` according to the <a href="codelists/environmental-impact">environmental impact mapping table</a>.

```xml
<cac:ProcurementAdditionalType>
  <cbc:ProcurementTypeCode listName="environmental-impact">circ-econ</cbc:ProcurementTypeCode>
</cac:ProcurementAdditionalType>
```

```json
{
  "tender": {
    "lots": [
      {
        "hasSustainability": true,
        "sustainability": [
          {
            "goal": "environmental.circularEconomy"
          }
        ]
      }
    ]
  }
}
```

</td>
      </tr>
      <tr id="BT-775-Lot">
        <td class="field break-all">
            <p><b>BT-775-Lot</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/procedure-lot-part-information.html#strategicProcurementSection"></a><br>Social Procurement</p><p><i>BT-775:</i> A social objective promoted by the works, supplies or services (e.g. fair working conditions).</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='Lot']/cac:ProcurementProject/cac:ProcurementAdditionalType/cbc:ProcurementTypeCode[@listName='social-objective']</span></code>
        </td>
        <td class="mapping">

<a href="operations.md#get-the-lot-for-a-procurementprojectlot">Get the lot for the ProcurementProjectLot</a> and set the lot's `.hasSustainability` to "true".

For each `cac:ProcurementAdditionalType` add a corresponding `.sustainability` object to the lot's `.sustainability` array.

- Map the code to the sustainability's `.goal` according to the <a href="codelists/social-objective">social objective mapping table</a>.
- Add 'awardCriteria', 'contractPerformanceConditions', 'selectionCriteria' and 'technicalSpecifications' to the sustainability's `.strategies` array.

```xml
<cac:ProcurementAdditionalType>
  <cbc:ProcurementTypeCode listName="social-objective">et-eq</cbc:ProcurementTypeCode>
</cac:ProcurementAdditionalType>
```

```json
{
  "tender": {
    "lots": [
      {
        "hasSustainability": true,
        "sustainability": [
          {
            "goal": "social.ethnicEquality",
            "strategies": [
              "awardCriteria",
              "contractPerformanceConditions",
              "selectionCriteria",
              "technicalSpecifications"
            ]
          }
        ]
      }
    ]
  }
}
```

</td>
      </tr>
      <tr id="BT-776-Lot">
        <td class="field break-all">
            <p><b>BT-776-Lot</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/procedure-lot-part-information.html#strategicProcurementSection"></a><br>Procurement of Innovation</p><p><i>BT-776:</i> An indication that innovative works, supplies or services are being bought. </p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='Lot']/cac:ProcurementProject/cac:ProcurementAdditionalType/cbc:ProcurementTypeCode[@listName='innovative-acquisition']</span></code>
        </td>
        <td class="mapping">

<a href="operations.md#get-the-lot-for-a-procurementprojectlot">Get the lot for the ProcurementProjectLot</a> and set the lot's `.hasSustainability` to "true".

For each `cac:ProcurementAdditionalType` add a corresponding `.sustainability` object to the lot's `.sustainability` array.

- Map the code to the sustainability's `.goal` according to the <a href="codelists/innovative-acquisition">innovative acquisition mapping table</a>.

```xml
<cac:ProcurementAdditionalType>
  <cbc:ProcurementTypeCode listName="innovative-acquisition">proc-innov</cbc:ProcurementTypeCode>
</cac:ProcurementAdditionalType>
```

```json
{
  "tender": {
    "lots": [
      {
        "hasSustainability": true,
        "sustainability": [
          {
            "goal": "economic.processInnovation"
          }
        ]
      }
    ]
  }
}
```

</td>
      </tr>
      <tr id="BT-777-Lot">
        <td class="field break-all">
            <p><b>BT-777-Lot</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/procedure-lot-part-information.html#strategicProcurementSection"></a><br>Strategic Procurement Description</p><p><i>BT-777:</i> Description of how the procurement procedure is aiming at reducing the environmental impacts of the procurement, fulfilling social objectives and/or buying an innovative work, supply or service.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='Lot']/cac:ProcurementProject/cac:ProcurementAdditionalType[cbc:ProcurementTypeCode/@listName='strategic-procurement']/cbc:ProcurementType</span></code>
        </td>
        <td class="mapping">

This field maps to the same `Sustainability` objects as created for BT-06-Lot.

<a href="operations.md#get-the-lot-for-a-procurementprojectlot">Get the lot for the ProcurementProjectLot</a> and for each `cbc:ProcurementTypeCode`, add or update the corresponding `Sustainability` object in the lot's `sustainability` array and map to its `.description`.

```xml
<cac:ProcurementAdditionalType>
  <cbc:ProcurementType languageID="ENG">This is a strategic procurement involving the innovative use of ...</cbc:ProcurementType>
</cac:ProcurementAdditionalType>
```

```json
{
  "tender": {
    "lots": [
      {
        "sustainability": [
          {
            "description": "This is a strategic procurement involving the innovative use of ..."
          }
        ]
      }
    ]
  }
}
```

</td>
      </tr>
      <tr id="BT-78-Lot">
        <td class="field break-all">
            <p><b>BT-78-Lot</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/procedure-lot-part-information.html#clearanceDeadlineSection"></a><br>Security Clearance Deadline</p><p><i>BT-78:</i> The time limit by which tenderers who do not hold a security clearance may obtain it.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='Lot']/cac:TenderingTerms/cbc:LatestSecurityClearanceDate</span></code>
        </td>
        <td class="mapping">

<a href="operations.md#get-the-lot-for-a-procurementprojectlot">Get the lot for the ProcurementProjectLot</a>, add a new `Milestone` object to the lot's `.milestones` array.

- Set its `id` incrementally.
- Set its `.type` to 'securityClearanceDeadline'.
- <a href="operations.md#convert-a-date-to-iso-format">Convert date to ISO format</a> and map to its `.dueDate`.

```xml
<cbc:LatestSecurityClearanceDate>2019-11-15+01:00</cbc:LatestSecurityClearanceDate>
```

```json
{
  "tender": {
    "lots": [
      {
        "milestones": [
          {
            "id": "1",
            "type": "securityClearanceDeadline",
            "dueDate": "2019-11-15T23:59:59+01:00"
          }
        ]
      }
    ]
  }
}
```

</td>
      </tr>
      <tr id="BT-79-Lot">
        <td class="field break-all">
            <p><b>BT-79-Lot</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/procedure-lot-part-information.html#staffQualificationSection"></a><br>Performing Staff Qualification</p><p><i>BT-79:</i> Whether the names and professional qualifications of the staff assigned to perform the contract must be given.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='Lot']/cac:TenderingTerms/cbc:RequiredCurriculaCode</span></code>
        </td>
        <td class="mapping">

<a href="operations.md#get-the-lot-for-a-procurementprojectlot">Get the lot for the ProcurementProjectLot</a>. If "par-requ" or "t-requ", set the lot's `.otherRequirements.requiresStaffNamesAndQualifications` to `true`. If "not-requ", set it to `false`. Otherwise, discard.

```xml
<cbc:RequiredCurriculaCode listName="requirement-stage">t-requ</cbc:RequiredCurriculaCode>
```

```json
{
  "tender": {
    "lots": [
      {
        "otherRequirements": {
          "requiresStaffNamesAndQualifications": true
        }
      }
    ]
  }
}
```

</td>
      </tr>
      <tr id="BT-801-Lot">
        <td class="field break-all">
            <p><b>BT-801-Lot</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/procedure-lot-part-information.html#nonDisclosureAgreementSection"></a><br>Non Disclosure Agreement</p><p><i>BT-801:</i> A non-disclosure agreement is required.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='Lot']/cac:TenderingTerms/cac:ContractExecutionRequirement[cbc:ExecutionRequirementCode/@listName='nda']/cbc:ExecutionRequirementCode[@listName='nda']</span></code>
        </td>
        <td class="mapping">

<a href="operations.md#get-the-lot-for-a-procurementprojectlot">Get the lot for the ProcurementProjectLot</a> and map to its `.contractTerms.hasNonDisclosureAgreement`.

```xml
<cac:ContractExecutionRequirement>
  <cbc:ExecutionRequirementCode listName="nda">true</cbc:ExecutionRequirementCode>
</cac:ContractExecutionRequirement>
```

```json
{
  "tender": {
    "lots": [
      {
        "contractTerms": {
          "hasNonDisclosureAgreement": "true"
        }
      }
    ]
  }
}
```

</td>
      </tr>
      <tr id="BT-802-Lot">
        <td class="field break-all">
            <p><b>BT-802-Lot</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/procedure-lot-part-information.html#nonDisclosureAgreementSection"></a><br>Non Disclosure Agreement Description</p><p><i>BT-802:</i> Additional information about the non-disclosure agreement.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='Lot']/cac:TenderingTerms/cac:ContractExecutionRequirement[cbc:ExecutionRequirementCode/@listName='nda']/cbc:Description</span></code>
        </td>
        <td class="mapping">

<a href="operations.md#get-the-lot-for-a-procurementprojectlot">Get the lot for the ProcurementProjectLot</a> and map to its `.contractTerms.nonDisclosureAgreement`.

```xml
<cac:ContractExecutionRequirement>
  <cbc:Description languageID="ENG">A Non Disclosure Agreement will need to ...</cbc:Description>
</cac:ContractExecutionRequirement>
```

```json
{
  "tender": {
    "lots": [
      {
        "contractTerms": {
          "nonDisclosureAgreement": "A Non Disclosure Agreement will need to ..."
        }
      }
    ]
  }
}
```

</td>
      </tr>
      <tr id="BT-803(d)-notice">
        <td class="field break-all">
            <p><b>BT-803(d)-notice</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/notice-information.html#dispatchDateEsender"></a><br>Notice Dispatch Date eSender (date)</p><p><i>BT-803:</i> The date and time the notice was transmitted electronically by the eSender to the Publications Office of the European Union</p>
            <code class="docutils literal notranslate"><span class="pre">/*/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efbc:TransmissionDate</span></code>
        </td>
        <td class="mapping">

Discard.

```xml
<efbc:TransmissionDate>2022-11-17+01:00</efbc:TransmissionDate>
```



</td>
      </tr>
      <tr id="BT-803(t)-notice">
        <td class="field break-all">
            <p><b>BT-803(t)-notice</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/notice-information.html#dispatchDateEsender"></a><br>Notice Dispatch Date eSender (time)</p><p><i>BT-803:</i> The date and time the notice was transmitted electronically by the eSender to the Publications Office of the European Union</p>
            <code class="docutils literal notranslate"><span class="pre">/*/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efbc:TransmissionTime</span></code>
        </td>
        <td class="mapping">

Discard.

```xml
<efbc:TransmissionTime>08:30:03+01:00</efbc:TransmissionTime>
```



</td>
      </tr>
      <tr id="BT-805-Lot">
        <td class="field break-all">
            <p><b>BT-805-Lot</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/procedure-lot-part-information.html#strategicProcurementSection"></a><br>Green Procurement Criteria</p><p><i>BT-805:</i> The procurement procedure includes the use of established green public procurement criteria (selection criteria, technical specifications, award criteria and contract performance clauses), at national, Union or other level, if applicable. </p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='Lot']/cac:ProcurementProject/cac:ProcurementAdditionalType[cbc:ProcurementTypeCode/@listName='gpp-criteria']/cbc:ProcurementTypeCode[@listName='gpp-criteria']</span></code>
        </td>
        <td class="mapping">

<a href="operations.md#get-the-lot-for-a-procurementprojectlot">Get the lot for the ProcurementProjectLot</a>.

If "none" discard, otherwise set the lot's `.hasSustainability` to "true".

For each `cac:ProcurementAdditionalType` add a corresponding `.sustainability` object to the lot's `.sustainability` array.

- Map the code to the sustainability's `.strategies` array according to the <a href="codelists/gpp-criteria">GPP criteria mapping table</a>.

```xml
<cac:ProcurementAdditionalType>
  <cbc:ProcurementTypeCode listName="gpp-criteria">eu</cbc:ProcurementTypeCode>
</cac:ProcurementAdditionalType>
```

```json
{
  "tender": {
    "lots": [
      {
        "hasSustainability": true,
        "sustainability": [
          {
            "strategies": [
              "euGPPCriteria"
            ]
          }
        ]
      }
    ]
  }
}
```

</td>
      </tr>
      <tr id="BT-88-Procedure">
        <td class="field break-all">
            <p><b>BT-88-Procedure</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/procedure-lot-part-information.html#procedureFeaturesSection"></a><br>Procedure Features</p><p><i>BT-88:</i> The main features of the procedure (e.g. description of the individual stage(s)) and information about where the full rules for the procedure can be found. This information shall be given when the procedure is not one of those mentioned in the procurement Directives. This can be the case for example for concessions, for social and other specific services, and in case of voluntary publication of procurement procedures below the EU procurement thresholds.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:TenderingProcess/cbc:Description</span></code>
        </td>
        <td class="mapping">

Map to `tender.procurementMethodDetails`

```xml
<cac:TenderingProcess>
  <cbc:Description languageID="ENG">A two stage procedure ...</cbc:Description>
</cac:TenderingProcess>
```

```json
{
  "tender": {
    "procurementMethodDetails": "A two stage procedure..."
  }
}
```

</td>
      </tr>
      <tr id="BT-92-Lot">
        <td class="field break-all">
            <p><b>BT-92-Lot</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/procedure-lot-part-information.html#postAwardSection"></a><br>Electronic Ordering</p><p><i>BT-92:</i> Electronic ordering will be used.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='Lot']/cac:TenderingTerms/cac:PostAwardProcess/cbc:ElectronicOrderUsageIndicator</span></code>
        </td>
        <td class="mapping">

<a href="operations.md#get-the-lot-for-a-procurementprojectlot">Get the lot for the ProcurementProjectLot</a> and map to its `.contractTerms.hasElectronicOrdering`.

```xml
<cac:PostAwardProcess>
  <cbc:ElectronicOrderUsageIndicator>true</cbc:ElectronicOrderUsageIndicator>
</cac:PostAwardProcess>
```

```json
{
  "tender": {
    "lots": [
      {
        "contractTerms": {
          "hasElectronicOrdering": true
        }
      }
    ]
  }
}
```

</td>
      </tr>
      <tr id="BT-93-Lot">
        <td class="field break-all">
            <p><b>BT-93-Lot</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/procedure-lot-part-information.html#postAwardSection"></a><br>Electronic Payment</p><p><i>BT-93:</i> Electronic payment will be used.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='Lot']/cac:TenderingTerms/cac:PostAwardProcess/cbc:ElectronicPaymentUsageIndicator</span></code>
        </td>
        <td class="mapping">

<a href="operations.md#get-the-lot-for-a-procurementprojectlot">Get the lot for the ProcurementProjectLot</a> and map to its `.contractTerms.hasElectronicPayment`.

```xml
<cac:PostAwardProcess>
  <cbc:ElectronicPaymentUsageIndicator>true</cbc:ElectronicPaymentUsageIndicator>
</cac:PostAwardProcess>
```

```json
{
  "tender": {
    "lots": [
      {
        "contractTerms": {
          "hasElectronicPayment": true
        }
      }
    ]
  }
}
```

</td>
      </tr>
      <tr id="BT-94-Lot">
        <td class="field break-all">
            <p><b>BT-94-Lot</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/procedure-lot-part-information.html#recurrenceSection"></a><br>Recurrence</p><p><i>BT-94:</i> Procurement whose purpose is likely to also be included in another procedure in the foreseeable future. (For example, a regularly re-tendered municipal service. This does not include awarding multiple contracts within a single qualification system, framework agreement, or a dynamic purchasing system.)</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='Lot']/cac:TenderingTerms/cbc:RecurringProcurementIndicator</span></code>
        </td>
        <td class="mapping">

<a href="operations.md#get-the-lot-for-a-procurementprojectlot">Get the lot for the ProcurementProjectLot</a> and map to its `.hasRecurrence`.

```xml
<cbc:RecurringProcurementIndicator>true</cbc:RecurringProcurementIndicator>
```

```json
{
  "tender": {
    "lots": [
      {
        "hasRecurrence": true
      }
    ]
  }
}
```

</td>
      </tr>
      <tr id="BT-95-Lot">
        <td class="field break-all">
            <p><b>BT-95-Lot</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/procedure-lot-part-information.html#recurrenceSection"></a><br>Recurrence Description</p><p><i>BT-95:</i> Any additional information about recurrence (e.g. estimated timing).</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='Lot']/cac:TenderingTerms/cbc:RecurringProcurementDescription</span></code>
        </td>
        <td class="mapping">

<a href="operations.md#get-the-lot-for-a-procurementprojectlot">Get the lot for the ProcurementProjectLot</a> and map to its `.recurrence.description`.

```xml
<cbc:RecurringProcurementDescription languageID="ENG">The current procurement ...</cbc:RecurringProcurementDescription>
```

```json
{
  "tender": {
    "lots": [
      {
        "recurrence": {
          "description": "The current procurement..."
        }
      }
    ]
  }
}
```

</td>
      </tr>
      <tr id="BT-97-Lot">
        <td class="field break-all">
            <p><b>BT-97-Lot</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/procedure-lot-part-information.html#tenderingLanguageSection"></a><br>Submission Language</p><p><i>BT-97:</i> A language in which tenders, requests to participate, or expressions of interest may be submitted.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='Lot']/cac:TenderingTerms/cac:Language/cbc:ID</span></code>
        </td>
        <td class="mapping">

<a href="operations.md#get-the-lot-for-a-procurementprojectlot">Get the lot for the ProcurementProjectLot</a>, map to ISO 639-1 in the <a href="https://op.europa.eu/en/web/eu-vocabularies/concept-scheme/-/resource?uri=http://publications.europa.eu/resource/authority/language">language authority table</a> and add to the lot's `.submissionTerms.languages` array.

```xml
<cac:Language>
  <cbc:ID>FRA</cbc:ID>
</cac:Language>
```

```json
{
  "tender": {
    "lots": [
      {
        "submissionTerms": {
          "languages": [
            "fr"
          ]
        }
      }
    ]
  }
}
```

</td>
      </tr>
      <tr id="BT-98-Lot">
        <td class="field break-all">
            <p><b>BT-98-Lot</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/procedure-lot-part-information.html#tenderValiditySection"></a><br>Tender Validity Deadline</p><p><i>BT-98:</i> The period, from the tender submission deadline, for which tenders must remain valid.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='Lot']/cac:TenderingTerms/cac:TenderValidityPeriod/cbc:DurationMeasure</span></code>
        </td>
        <td class="mapping">

<a href="operations.md#get-the-lot-for-a-procurementprojectlot">Get the lot for the ProcurementProjectLot</a>.

Multiply by:

- 1, if @unitCode="DAY".
- 7, if @unitCode="WEEK".
- 30, if @unitCode="MONTH".
- 365, if @unitCode="YEAR".

Map to the lot's `.submissionTerms.bidValidityPeriod.durationInDays`.

```xml
<cac:TenderValidityPeriod>
  <cbc:DurationMeasure unitCode="MONTH">4</cbc:DurationMeasure>
</cac:TenderValidityPeriod>
```

```json
{
  "tender": {
    "lots": [
      {
        "submissionTerms": {
          "bidValidityPeriod": {
            "durationInDays": 120
          }
        }
      }
    ]
  }
}
```

</td>
      </tr>
      <tr id="BT-99-Lot">
        <td class="field break-all">
            <p><b>BT-99-Lot</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/procedure-lot-part-information.html#appealTermsSection"></a><br>Review Deadline Description</p><p><i>BT-99:</i> The description of the time limits for review procedures.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='Lot']/cac:TenderingTerms/cac:AppealTerms/cac:PresentationPeriod/cbc:Description</span></code>
        </td>
        <td class="mapping">

<a href="operations.md#get-the-lot-for-a-procurementprojectlot">Get the lot for the ProcurementProjectLot</a> and map to its `.reviewDetails`.

```xml
<cac:PresentationPeriod>
  <cbc:Description languageID="ENG">Any review request shall be submitted ...</cbc:Description>
</cac:PresentationPeriod>
```

```json
{
  "tender": {
    "lots": [
      {
        "reviewDetails": "Any review request shall be submitted ..."
      }
    ]
  }
}
```

</td>
      </tr>
      <tr id="OPA-118-NoticeResult-Currency">
        <td class="field break-all">
            <p><b>OPA-118-NoticeResult-Currency</b> <br>Currency of the notice framework value</p><p><i>BT-118:</i> The maximum value which can be spent within the framework agreement(s) announced in this notice over its/their whole duration, in all lots, including options and renewals, as calculated on the basis of the winner’s tender or winners’ tenders.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:NoticeResult/efbc:OverallMaximumFrameworkContractsAmount/@currencyID</span></code>
        </td>
        <td class="mapping">

Discard





</td>
      </tr>
      <tr id="OPA-161-NoticeResult-Currency">
        <td class="field break-all">
            <p><b>OPA-161-NoticeResult-Currency</b> <br>Currency of the notice value</p><p><i>BT-161:</i> The value of all contracts awarded in this notice, including options and renewals.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:NoticeResult/cbc:TotalAmount/@currencyID</span></code>
        </td>
        <td class="mapping">

Discard





</td>
      </tr>
      <tr id="OPA-27-Procedure-Currency">
        <td class="field break-all">
            <p><b>OPA-27-Procedure-Currency</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/procedure-lot-part-information.html#estimatedValueSection"></a><br>Currency of the estimated value of the procedure</p><p><i>BT-27:</i> The estimated value of the procurement procedure or lot, over its whole duration, including options and renewals.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProject/cac:RequestedTenderTotal/cbc:EstimatedOverallContractAmount/@currencyID</span></code>
        </td>
        <td class="mapping">

Follow guidance for BT-27-Procedure.

```xml
<cac:RequestedTenderTotal>
  <cbc:EstimatedOverallContractAmount currencyID="EUR">250000</cbc:EstimatedOverallContractAmount>
</cac:RequestedTenderTotal>
```

```json
{
  "tender": {
    "value": {
      "amount": 250000,
      "currency": "EUR"
    }
  }
}
```

</td>
      </tr>
      <tr id="OPA-36-Lot-Number">
        <td class="field break-all">
            <p><b>OPA-36-Lot-Number</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/procedure-lot-part-information.html#plannedPeriodSection"></a><br>Numeric value of the duration period</p><p><i>BT-36:</i> The (estimated) period from the start to the end of the contract, framework agreement, dynamic purchasing system or qualification system. This shall include any options and renewals.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='Lot']/cac:ProcurementProject/cac:PlannedPeriod/cbc:DurationMeasure</span></code>
        </td>
        <td class="mapping">

Follow guidance for BT-36-Lot.

```xml
<cac:PlannedPeriod>
  <cbc:DurationMeasure unitCode="DAY">3</cbc:DurationMeasure>
</cac:PlannedPeriod>
```

```json
{
  "tender": {
    "lots": [
      {
        "contractPeriod": {
          "durationInDays": 3
        }
      }
    ]
  }
}
```

</td>
      </tr>
      <tr id="OPA-36-Part-Number">
        <td class="field break-all">
            <p><b>OPA-36-Part-Number</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/procedure-lot-part-information.html#plannedPeriodSection"></a><br>Numeric value of the duration period</p><p><i>BT-36:</i> The (estimated) period from the start to the end of the contract, framework agreement, dynamic purchasing system or qualification system. This shall include any options and renewals.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='Part']/cac:ProcurementProject/cac:PlannedPeriod/cbc:DurationMeasure</span></code>
        </td>
        <td class="mapping">

Follow guidance for BT-36-Part.

```xml
<cac:PlannedPeriod>
  <cbc:DurationMeasure unitCode="DAY">3</cbc:DurationMeasure>
</cac:PlannedPeriod>
```

```json
{
  "tender": {
    "contractPeriod": {
      "durationInDays": 3
    }
  }
}
```

</td>
      </tr>
      <tr id="OPA-98-Lot-Number">
        <td class="field break-all">
            <p><b>OPA-98-Lot-Number</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/procedure-lot-part-information.html#tenderValiditySection"></a><br>Numeric value of the tender validity deadline</p><p><i>BT-98:</i> The period, from the tender submission deadline, for which tenders must remain valid.</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='Lot']/cac:TenderingTerms/cac:TenderValidityPeriod/cbc:DurationMeasure</span></code>
        </td>
        <td class="mapping">

Follow guidance for BT-98-Lot.

```xml
<cac:TenderValidityPeriod>
  <cbc:DurationMeasure unitCode="MONTH">4</cbc:DurationMeasure>
</cac:TenderValidityPeriod>
```

```json
{
  "tender": {
    "lots": [
      {
        "submissionTerms": {
          "bidValidityPeriod": {
            "durationInDays": 120
          }
        }
      }
    ]
  }
}
```

</td>
      </tr>
      <tr id="OPP-010-notice">
        <td class="field break-all">
            <p><b>OPP-010-notice</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/notice-information.html#pubInfoSection"></a><br>Notice Publication Number</p>
            <code class="docutils literal notranslate"><span class="pre">/*/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:Publication/efbc:NoticePublicationID[@schemeName='ojs-notice-id']</span></code>
        </td>
        <td class="mapping">

Discard.

```xml
<efac:Publication>
  <efbc:NoticePublicationID schemeName="ojs-notice-id">12345678-2023</efbc:NoticePublicationID>
</efac:Publication>
```



</td>
      </tr>
      <tr id="OPP-011-notice">
        <td class="field break-all">
            <p><b>OPP-011-notice</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/notice-information.html#pubInfoSection"></a><br>OJEU Identifier</p>
            <code class="docutils literal notranslate"><span class="pre">/*/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:Publication/efbc:GazetteID[@schemeName='ojs-id']</span></code>
        </td>
        <td class="mapping">

Discard.

```xml
<efac:Publication>
  <efbc:GazetteID schemeName="ojs-id">123/2023</efbc:GazetteID>
</efac:Publication>
```



</td>
      </tr>
      <tr id="OPP-012-notice">
        <td class="field break-all">
            <p><b>OPP-012-notice</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/notice-information.html#pubInfoSection"></a><br>OJEU Publication Date</p>
            <code class="docutils literal notranslate"><span class="pre">/*/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:Publication/efbc:PublicationDate</span></code>
        </td>
        <td class="mapping">

Discard.

```xml
<efac:Publication>
  <efbc:PublicationDate>2023-03-14+01:00</efbc:PublicationDate>
</efac:Publication>
```



</td>
      </tr>
      <tr id="OPP-020-Contract">
        <td class="field break-all">
            <p><b>OPP-020-Contract</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/competition-results.html#settledContractSection"></a><br>Assets related contract extension indicator</p>
            <code class="docutils literal notranslate"><span class="pre">/*/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:NoticeResult/efac:SettledContract/efac:DurationJustification/efbc:ExtendedDurationIndicator</span></code>
        </td>
        <td class="mapping">

<a href="common-operations.md#get-the-lots-for-settledcontract">Get the lots for the SettledContract</a> and map to each lot's `.hasEssentialAssets`.

```xml
<efac:SettledContract>
  <efac:DurationJustification>
    <efbc:ExtendedDurationIndicator>true</efbc:ExtendedDurationIndicator>
  </efac:DurationJustification>
</efac:SettledContract>
```

```json
{
  "tender": {
    "lots": [
      {
        "hasEssentialAssets": true
      }
    ]
  }
}
```

</td>
      </tr>
      <tr id="OPP-021-Contract">
        <td class="field break-all">
            <p><b>OPP-021-Contract</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/competition-results.html#settledContractSection"></a><br>Used asset</p>
            <code class="docutils literal notranslate"><span class="pre">/*/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:NoticeResult/efac:SettledContract/efac:DurationJustification/efac:AssetsList/efac:Asset/efbc:AssetDescription</span></code>
        </td>
        <td class="mapping">

This field maps to the same `EssentialAssets` objects created for OPP-022-Contract and OPP-023-Contract.

<a href="common-operations.md#get-the-lots-for-settledcontract">Get the lots for the SettledContract</a>. For each lot, add or update the corresponding `EssentialAssets` object in the lot's `.essentialAssets` array and map to its `.description`.

```xml
<efac:SettledContract>
  <efac:DurationJustification>
    <efac:AssetsList>
      <efac:Asset>
        <efbc:AssetDescription languageID="SPA">Asset 1 blabla</efbc:AssetDescription>
      </efac:Asset>
    </efac:AssetsList>
  </efac:DurationJustification>
</efac:SettledContract>
```

```json
{
  "tender": {
    "lots": [
      {
        "essentialAssets": [
          {
            "description": "Asset 1 blabla"
          }
        ]
      }
    ]
  }
}
```

</td>
      </tr>
      <tr id="OPP-022-Contract">
        <td class="field break-all">
            <p><b>OPP-022-Contract</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/competition-results.html#settledContractSection"></a><br>Significance (%)</p>
            <code class="docutils literal notranslate"><span class="pre">/*/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:NoticeResult/efac:SettledContract/efac:DurationJustification/efac:AssetsList/efac:Asset/efbc:AssetSignificance</span></code>
        </td>
        <td class="mapping">

This field maps to the same `EssentialAssets` objects created for OPP-021-Contract and OPP-023-Contract.

<a href="common-operations.md#get-the-lots-for-settledcontract">Get the lots for the SettledContract</a>. For each lot, add or update the corresponding `EssentialAssets` object in the lot's `.essentialAssets` array and map to its `.significance`.

```xml
<efac:SettledContract>
  <efac:DurationJustification>
    <efac:AssetsList>
      <efac:Asset>
        <efbc:AssetSignificance languageID="SPA">30</efbc:AssetSignificance>
      </efac:Asset>
    </efac:AssetsList>
  </efac:DurationJustification>
</efac:SettledContract>
```

```json
{
  "tender": {
    "lots": [
      {
        "essentialAssets": [
          {
            "significance": "30"
          }
        ]
      }
    ]
  }
}
```

</td>
      </tr>
      <tr id="OPP-023-Contract">
        <td class="field break-all">
            <p><b>OPP-023-Contract</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/competition-results.html#settledContractSection"></a><br>Predominance (%)</p>
            <code class="docutils literal notranslate"><span class="pre">/*/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:NoticeResult/efac:SettledContract/efac:DurationJustification/efac:AssetsList/efac:Asset/efbc:AssetPredominance</span></code>
        </td>
        <td class="mapping">

This field maps to the same `EssentialAssets` objects created for OPP-021-Contract and OPP-022-Contract.

<a href="common-operations.md#get-the-lots-for-settledcontract">Get the lots for the SettledContract</a>. For each lot, add or update the corresponding `EssentialAssets` object in the lot's `.essentialAssets` array and map to its `.predominance`.

```xml
<efac:SettledContract>
  <efac:DurationJustification>
    <efac:AssetsList>
      <efac:Asset>
        <efbc:AssetPredominance languageID="SPA">40</efbc:AssetPredominance>
      </efac:Asset>
    </efac:AssetsList>
  </efac:DurationJustification>
</efac:SettledContract>
```

```json
{
  "tender": {
    "lots": [
      {
        "essentialAssets": [
          {
            "predominance": "40"
          }
        ]
      }
    ]
  }
}
```

</td>
      </tr>
      <tr id="OPP-030-Tender">
        <td class="field break-all">
            <p><b>OPP-030-Tender</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/competition-results.html#lotTenderSection"></a><br>Contract conditions Code</p>
            <code class="docutils literal notranslate"><span class="pre">/*/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:NoticeResult/efac:LotTender/efac:ContractTerm[not(efbc:TermCode/text()='all-rev-tic')][efbc:TermCode/@listName='contract-detail']/efbc:TermCode</span></code>
        </td>
        <td class="mapping">

Discard.

```xml
<efac:ContractTerm>
  <efbc:TermCode listName="contract-detail">soc-stand</efbc:TermCode>
</efac:ContractTerm>
```



</td>
      </tr>
      <tr id="OPP-031-Tender">
        <td class="field break-all">
            <p><b>OPP-031-Tender</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/competition-results.html#lotTenderSection"></a><br>Contract Conditions Description (other than revenue allocation)</p>
            <code class="docutils literal notranslate"><span class="pre">/*/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:NoticeResult/efac:LotTender/efac:ContractTerm[not(efbc:TermCode/text()='all-rev-tic')][efbc:TermCode/@listName='contract-detail']/efbc:TermDescription</span></code>
        </td>
        <td class="mapping">

This mapping assumes that the value of this field is consistent across all the LotTenders for a given lot. If the values in your data source vary, contact the <a href="mailto:data@open-contracting.org">OCDS Data Support Team</a>.

If the value of `ancestor::ContractTerm/efbc:TermCode` is `all-rev-tic`, discard. Otherwise, <a href="common-operations.md#get-the-lot-for-a-lottender">get the lot for the lot tender</a>.

If the value of `ancestor::ContractTerm/efbc:TermCode` is `exc-right`, set the lot's `contractTerms.hasExclusiveRights` to `true`. Otherwise,  map to the lot's `.contractTerms` according to the value of `ancestor::ContractTerm/efbc:TermCode`:

```
* `cost-comp`: Map to `contractTerms.financialTerms`
* `other`:  Map to `contractTerms.otherTerms`
* `publ-ser-obl`: Map to `contractTerms.performanceTerms`
* `soc-stand`: Map to `contractTerms.socialStandards`
```

```xml
<efac:ContractTerm>
  <efbc:TermCode listName="contract-detail">soc-stand</efbc:TermCode>
  <efbc:TermDescription languageID="ENG">Description of the social-standards blablabla ...</efbc:TermDescription>
</efac:ContractTerm>
```

```json
{
  "tender": {
    "lots": [
      {
        "contractTerms": {
          "socialStandards": "Description of the social-standards blablabla ..."
        }
      }
    ]
  }
}
```

</td>
      </tr>
      <tr id="OPP-032-Tender">
        <td class="field break-all">
            <p><b>OPP-032-Tender</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/competition-results.html#lotTenderSection"></a><br>Revenues Allocation</p>
            <code class="docutils literal notranslate"><span class="pre">/*/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:NoticeResult/efac:LotTender/efac:ContractTerm[efbc:TermCode/text()='all-rev-tic']/efbc:TermPercent</span></code>
        </td>
        <td class="mapping">

This mapping assumes that the value of this field is consistent across all the LotTenders for a given lot. If the values in your data source vary, contact the <a href="mailto:data@open-contracting.org">OCDS Data Support Team</a>.

<a href="common-operations.md#get-the-lot-for-a-lottender">Get the lot for the lot tender</a>, divide by 100 and map the result to the lot's `.contractTerms.operatorRevenueShare`.

```xml
<efac:ContractTerm>
  <efbc:TermCode>all-rev-ic</efbc:TermCode>
  <efbc:TermPercent>100</efbc:TermPercent>
</efac:ContractTerm>
```

```json
{
  "tender": {
    "lots": [
      {
        "contractTerms": {
          "operatorRevenueShare": 1
        }
      }
    ]
  }
}
```

</td>
      </tr>
      <tr id="OPP-033-Tender">
        <td class="field break-all">
            <p><b>OPP-033-Tender</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/competition-results.html#lotTenderSection"></a><br>Penalties and Rewards Code</p>
            <code class="docutils literal notranslate"><span class="pre">/*/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:NoticeResult/efac:LotTender/efac:ContractTerm[efbc:TermCode/@listName='rewards-penalties']/efbc:TermCode</span></code>
        </td>
        <td class="mapping">

Discard.

```xml
<efac:ContractTerm>
  <efbc:TermCode listName="rewards-penalties">rew-pen</efbc:TermCode>
</efac:ContractTerm>
```



</td>
      </tr>
      <tr id="OPP-034-Tender">
        <td class="field break-all">
            <p><b>OPP-034-Tender</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/competition-results.html#lotTenderSection"></a><br>Penalties and Rewards Description</p>
            <code class="docutils literal notranslate"><span class="pre">/*/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:NoticeResult/efac:LotTender/efac:ContractTerm[efbc:TermCode/@listName='rewards-penalties']/efbc:TermDescription</span></code>
        </td>
        <td class="mapping">

This mapping assumes that the value of this field is consistent across all the LotTenders for a given lot. If the values in your data source vary, contact the <a href="mailto:data@open-contracting.org">OCDS Data Support Team</a>.

<a href="common-operations.md#get-the-lot-for-a-lottender">Get the lot for the lot tender</a> and map to its `.contractTerms.rewardsAndPenalties`.

```xml
<efac:ContractTerm>
  <efbc:TermCode listName="rewards-penalties">rew-pen</efbc:TermCode>
  <efbc:TermDescription languageID="ENG">Information on Rewards and Penalties ....</efbc:TermDescription>
</efac:ContractTerm>
```

```json
{
  "tender": {
    "lots": [
      {
        "contractTerms": {
          "rewardsAndPenalties": "Information on Rewards and Penalties ...."
        }
      }
    ]
  }
}
```

</td>
      </tr>
      <tr id="OPP-040-Procedure">
        <td class="field break-all">
            <p><b>OPP-040-Procedure</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/procedure-lot-part-information.html#natureSection"></a><br>Main Nature - Sub Type</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProject/cac:ProcurementAdditionalType/cbc:ProcurementTypeCode[@listName='transport-service']</span></code>
        </td>
        <td class="mapping">

Add to `tender.additionalProcurementCategories` array.

```xml
<cac:ProcurementAdditionalType>
  <cbc:ProcurementTypeCode listName="transport-service">bus-s</cbc:ProcurementTypeCode>
</cac:ProcurementAdditionalType>
```

```json
{
  "tender": {
    "additionalProcurementCategories": [
      "bus-s"
    ]
  }
}
```

</td>
      </tr>
      <tr id="OPP-050-Organization">
        <td class="field break-all">
            <p><b>OPP-050-Organization</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/parties.html#buyerSection"></a><br>Buyers Group Lead Indicator</p>
            <code class="docutils literal notranslate"><span class="pre">/*/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:Organizations/efac:Organization/efbc:GroupLeadIndicator</span></code>
        </td>
        <td class="mapping">

If the value is "false" then discard. Otherwise <a href="operations.md#get-the-organization-for-a-company">get the organization for the company</a> and add 'leadBuyer' to the organization's `.roles` array.

```xml
<efac:Organization>
  <efbc:GroupLeadIndicator>true</efbc:GroupLeadIndicator>
</efac:Organization>
```

```json
{
  "parties": [
    {
      "id": "ORG-0001",
      "roles": [
        "leadBuyer"
      ]
    }
  ]
}
```

</td>
      </tr>
      <tr id="OPP-051-Organization">
        <td class="field break-all">
            <p><b>OPP-051-Organization</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/parties.html#buyerSection"></a><br>Awarding CPB Buyer Indicator</p>
            <code class="docutils literal notranslate"><span class="pre">/*/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:Organizations/efac:Organization/efbc:AwardingCPBIndicator</span></code>
        </td>
        <td class="mapping">

If the value is "false" then discard. Otherwise <a href="operations.md#get-the-organization-for-a-company">get the organization for the company</a> and add 'awardingCentralPurchasingBody' to the organization's `.roles` array.

```xml
<efac:Organization>
  <efbc:AwardingCPBIndicator>true</efbc:AwardingCPBIndicator>
</efac:Organization>
```

```json
{
  "parties": [
    {
      "id": "ORG-0001",
      "roles": [
        "awardingCentralPurchasingBody"
      ]
    }
  ]
}
```

</td>
      </tr>
      <tr id="OPP-052-Organization">
        <td class="field break-all">
            <p><b>OPP-052-Organization</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/parties.html#buyerSection"></a><br>Acquiring CPB Buyer Indicator</p>
            <code class="docutils literal notranslate"><span class="pre">/*/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:Organizations/efac:Organization/efbc:AcquiringCPBIndicator</span></code>
        </td>
        <td class="mapping">

If the value is "false" then discard. Otherwise <a href="operations.md#get-the-organization-for-a-company">get the organization for the company</a> and add 'acquiringCentralPurchasingBody' to the organization's `.roles` array.

```xml
<efac:Organization>
  <efbc:AcquiringCPBIndicator>true</efbc:AcquiringCPBIndicator>
</efac:Organization>
```

```json
{
  "parties": [
    {
      "id": "ORG-0001",
      "roles": [
        "acquiringCentralPurchasingBody"
      ]
    }
  ]
}
```

</td>
      </tr>
      <tr id="OPP-070-notice">
        <td class="field break-all">
            <p><b>OPP-070-notice</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/notice-information.html#subtypeSection"></a><br>Notice Subtype</p>
            <code class="docutils literal notranslate"><span class="pre">/*/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:NoticeSubType/cbc:SubTypeCode</span></code>
        </td>
        <td class="mapping">

Discard.

```xml
<efac:NoticeSubType>
  <cbc:SubTypeCode listName="notice-subtype">16</cbc:SubTypeCode>
</efac:NoticeSubType>
```



</td>
      </tr>
      <tr id="OPP-080-Tender">
        <td class="field break-all">
            <p><b>OPP-080-Tender</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/competition-results.html#lotTenderSection"></a><br>Kilometers Public Transport</p>
            <code class="docutils literal notranslate"><span class="pre">/*/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:NoticeResult/efac:LotTender/efbc:PublicTransportationCumulatedDistance</span></code>
        </td>
        <td class="mapping">

Map to the contract's .publicPassengerTransportServicesKilometers

```xml
<efac:LotTender>
  <efbc:PublicTransportationCumulatedDistance unitCode="km">988754432110987</efbc:PublicTransportationCumulatedDistance>
</efac:LotTender>
```

```json
{
  "awards": [
    {
      "publicPassengerTransportServicesKilometers": "988754432110987"
    }
  ]
}
```

</td>
      </tr>
      <tr id="OPP-090-Procedure">
        <td class="field break-all">
            <p><b>OPP-090-Procedure</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/procedure-lot-part-information.html#previousNoticeSection"></a><br>Previous Notice Identifier</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:TenderingProcess/cac:NoticeDocumentReference/cbc:ID</span></code>
        </td>
        <td class="mapping">

<a href="operations.md#reference-a-previous-publication">Reference a previous publication</a>. If OPP-090-Procedure is repeated set the relatedProcess's `id` incrementally.

```xml
<cac:NoticeDocumentReference>
  <cbc:ID schemeName="notice-id-ref">123e4567-e89b-12d3-a456-426614174000-06</cbc:ID>
</cac:NoticeDocumentReference>
```

```json
{
  "relatedProcesses": [
    {
      "id": "1",
      "relationship": [
        "planning"
      ],
      "scheme": "eu-oj",
      "identifier": "123e4567-e89b-12d3-a456-426614174000-06"
    }
  ]
}
```

</td>
      </tr>
      <tr id="OPT-001-notice">
        <td class="field break-all">
            <p><b>OPT-001-notice</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/identifiers.html#identifiersSection"></a><br>UBL version ID (UBL)</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cbc:UBLVersionID</span></code>
        </td>
        <td class="mapping">

Discard.

```xml
<cbc:UBLVersionID>2.3</cbc:UBLVersionID>
```



</td>
      </tr>
      <tr id="OPT-002-notice">
        <td class="field break-all">
            <p><b>OPT-002-notice</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/identifiers.html#identifiersSection"></a><br>Customization ID (UBL)</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cbc:CustomizationID</span></code>
        </td>
        <td class="mapping">

Discard.

```xml
<cbc:CustomizationID>eforms-sdk-1.4</cbc:CustomizationID>
```



</td>
      </tr>
      <tr id="OPT-030-Procedure-SProvider">
        <td class="field break-all">
            <p><b>OPT-030-Procedure-SProvider</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/parties.html#_buyer_and_service_providers"></a><br>Provided Service Type</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ContractingParty/cac:Party/cac:ServiceProviderParty/cbc:ServiceTypeCode</span></code>
        </td>
        <td class="mapping">

Get the `Organization` in `parties` whose `id` is equal to the value of `ancestor::cac:ServiceProviderParty/cac:Party/cac:PartyIdentification/cbc:ID`. If none exists yet:

- Add an `Organization` to `parties`.
- Set its `.id` to the value of `ancestor::cac:ServiceProviderParty/cac:Party/cac:PartyIdentification/cbc:ID`.

If the value of the field is "serv-prov" add `procurementServiceProvider` to the organization's `.roles` array. If the value of the field is "ted-esen" add `eSender` to the organization's `.roles` array.

```xml
<cac:ServiceProviderParty>
  <cbc:ServiceTypeCode listName="organisation-role">ted-esen</cbc:ServiceTypeCode>
</cac:ServiceProviderParty>
```

```json
{
  "parties": [
    {
      "roles": [
        "eSender"
      ]
    }
  ]
}
```

</td>
      </tr>
      <tr id="OPT-050-Lot">
        <td class="field break-all">
            <p><b>OPT-050-Lot</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/procedure-lot-part-information.html#procurementDocsSection"></a><br>Document Status</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='Lot']/cac:TenderingTerms/cac:CallForTendersDocumentReference/cbc:DocumentStatusCode</span></code>
        </td>
        <td class="mapping">

Discard. If "true" follow the guidance for <a href="#BT-708-Lot">BT-708-Lot</a>, if "false" follow the guidance for <a href="#BT-737-Lot">BT-737-Lot</a>

```xml
<cac:CallForTendersDocumentReference>
  <cbc:DocumentStatusCode listName="linguistic-status">official</cbc:DocumentStatusCode>
</cac:CallForTendersDocumentReference>
```



</td>
      </tr>
      <tr id="OPT-050-Part">
        <td class="field break-all">
            <p><b>OPT-050-Part</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/procedure-lot-part-information.html#procurementDocsSection"></a><br>Document Status</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='Part']/cac:TenderingTerms/cac:CallForTendersDocumentReference/cbc:DocumentStatusCode</span></code>
        </td>
        <td class="mapping">

Discard. If "true" follow the guidance for <a href="#BT-708-Part">BT-708-Part</a>, if "false" follow the guidance for <a href="#BT-737-Part">BT-737-Part</a>

```xml
<cac:CallForTendersDocumentReference>
  <cbc:DocumentStatusCode listName="linguistic-status">official</cbc:DocumentStatusCode>
</cac:CallForTendersDocumentReference>
```



</td>
      </tr>
      <tr id="OPT-070-Lot">
        <td class="field break-all">
            <p><b>OPT-070-Lot</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/procedure-lot-part-information.html#reservedExecutionSection"></a><br>Reserved Execution justification</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='Lot']/cac:TenderingTerms/cac:ContractExecutionRequirement[cbc:ExecutionRequirementCode/@listName='reserved-execution']/cbc:Description</span></code>
        </td>
        <td class="mapping">

Discard. OPT-070 may only be used in some circumstances for a Call for Expression of Interest, which is not covered by the eForms regulation.





</td>
      </tr>
      <tr id="OPT-071-Lot">
        <td class="field break-all">
            <p><b>OPT-071-Lot</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/procedure-lot-part-information.html#tenderingTermsSection"></a><br>Quality Target Code</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='Lot']/cac:TenderingTerms/cac:ContractExecutionRequirement[cbc:ExecutionRequirementCode/@listName='customer-service']/cbc:ExecutionRequirementCode</span></code>
        </td>
        <td class="mapping">

<a href="operations.md#get-the-lot-for-a-procurementprojectlot">Get the lot for the ProcurementProjectLot</a> and add a `CustomerServices` object to its `contractTerms` array.

- Map to its `.type`.
- Look up the code's label in the <a href="https://op.europa.eu/en/web/eu-vocabularies/concept-scheme/-/resource?uri=http://publications.europa.eu/resource/authority/customer-service">authority table</a> and map it to `.name`.

```xml
<cac:ContractExecutionRequirement>
  <cbc:ExecutionRequirementCode listName="customer-service">clean</cbc:ExecutionRequirementCode>
</cac:ContractExecutionRequirement>
```

```json
{
  "tender": {
    "lots": [
      {
        "contractTerms": {
          "customerServices": [
            {
              "type": "clean",
              "name": "Cleanliness of rolling stock and station facilities"
            }
          ]
        }
      }
    ]
  }
}
```

</td>
      </tr>
      <tr id="OPT-072-Lot">
        <td class="field break-all">
            <p><b>OPT-072-Lot</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/procedure-lot-part-information.html#tenderingTermsSection"></a><br>Quality Target Description</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='Lot']/cac:TenderingTerms/cac:ContractExecutionRequirement[cbc:ExecutionRequirementCode/@listName='customer-service']/cbc:Description</span></code>
        </td>
        <td class="mapping">

These values map to the same `CustomerServices` objects as created for OPT-071-Lot.

<a href="operations.md#get-the-lot-for-a-procurementprojectlot">Get the lot for the ProcurementProjectLot</a>.

For each `cac:ContractExecutionRequirement` add or update the corresponding `CustomerServices` object in the lot's `contractTerms` array and map to its `.description`.

```xml
<cac:ContractExecutionRequirement>
  <cbc:ExecutionRequirementCode listName="customer-service">clean</cbc:ExecutionRequirementCode>
</cac:ContractExecutionRequirement>
```

```json
{
  "tender": {
    "lots": [
      {
        "contractTerms": {
          "customerServices": [
            {
              "description": "A description as given in OPT-072"
            }
          ]
        }
      }
    ]
  }
}
```

</td>
      </tr>
      <tr id="OPT-090-Lot">
        <td class="field break-all">
            <p><b>OPT-090-Lot</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/procedure-lot-part-information.html#frameworkAgreementSection"></a><br>Buyer Categories</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='Lot']/cac:TenderingProcess/cac:FrameworkAgreement/cac:SubsequentProcessTenderRequirement[cbc:Name/text()='buyer-categories']/cbc:Name</span></code>
        </td>
        <td class="mapping">

Discard

```xml
<cac:SubsequentProcessTenderRequirement>
  <cbc:Name>buyer-categories</cbc:Name>
</cac:SubsequentProcessTenderRequirement>
```



</td>
      </tr>
      <tr id="OPT-100-Contract">
        <td class="field break-all">
            <p><b>OPT-100-Contract</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/competition-results.html#settledContractSection"></a><br>Framework Notice Identifier</p>
            <code class="docutils literal notranslate"><span class="pre">/*/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:NoticeResult/efac:SettledContract/cac:NoticeDocumentReference/cbc:ID</span></code>
        </td>
        <td class="mapping">

Add a `RelatedProcess` to the contract's `.relatedProcesses` array, and:

- Set its `.id` incrementally.
- Add 'framework' to its `.relationship` array.
- If the referenced notice is available in OCDS:
  - Set `.scheme` to 'ocid'.
  - Set `.identifier` to the `.ocid` of the referenced notice.
- Otherwise:
  - Set `.scheme` to the value of `cbc:ID[@schemeName]`.
  - Map `cbc:ID` to `.identifier`.

```xml
<efac:NoticeResult>
  <efac:SettledContract>
    <cac:NoticeDocumentReference>
      <cbc:ID schemeName="ojs-notice-id">62783-2020</cbc:ID>
    </cac:NoticeDocumentReference>
  </efac:SettledContract>
</efac:NoticeResult>
```

```json
{
  "relatedProcesses": [
    {
      "id": "1",
      "scheme": "ojs-notice-id",
      "identifier": "62783-2020"
    }
  ]
}
```

</td>
      </tr>
      <tr id="OPT-110-Lot-FiscalLegis">
        <td class="field break-all">
            <p><b>OPT-110-Lot-FiscalLegis</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/parties.html#_legislation_information_provider"></a><br>URL to Fiscal Legislation</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='Lot']/cac:TenderingTerms/cac:FiscalLegislationDocumentReference/cac:Attachment/cac:ExternalReference/cbc:URI</span></code>
        </td>
        <td class="mapping">

<a href="operations.md#get-the-document-for-a-document-reference">Get the document for the document reference</a>.

Map to the document's `.url`.

<a href="operations.md#get-the-lot-for-a-procurementprojectlot">Get the lot for the ProcurementProjectLot</a> and add its `id` to the document's `.relatedLots`.

```xml
<cac:ProcurementProjectLot>
  <cbc:ID schemeName="Lot">LOT-0001</cbc:ID>
  <cac:TenderingTerms>
    <cac:FiscalLegislationDocumentReference>
      <cbc:ID>Fiscal1</cbc:ID>
      <cac:Attachment>
        <cac:ExternalReference>
          <cbc:URI>https://fiscal-legislation.gov.stat</cbc:URI>
        </cac:ExternalReference>
      </cac:Attachment>
    </cac:FiscalLegislationDocumentReference>
  </cac:TenderingTerms>
</cac:ProcurementProjectLot>
```

```json
{
  "tender": {
    "documents": [
      {
        "id": "Fiscal1",
        "url": "https://fiscal-legislation.gov.stat",
        "relatedLots": [
          "LOT-0001"
        ]
      }
    ]
  }
}
```

</td>
      </tr>
      <tr id="OPT-110-Part-FiscalLegis">
        <td class="field break-all">
            <p><b>OPT-110-Part-FiscalLegis</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/parties.html#_legislation_information_provider"></a><br>URL to Fiscal Legislation</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='Part']/cac:TenderingTerms/cac:FiscalLegislationDocumentReference/cac:Attachment/cac:ExternalReference/cbc:URI</span></code>
        </td>
        <td class="mapping">

<a href="operations.md#get-the-document-for-a-document-reference">Get the document for the document reference</a>.

Map to the document's `.url`.

```xml
<cac:FiscalLegislationDocumentReference>
  <cbc:ID>Fiscal1</cbc:ID>
  <cac:Attachment>
    <cac:ExternalReference>
      <cbc:URI>https://fiscal-legislation.gov.stat</cbc:URI>
    </cac:ExternalReference>
  </cac:Attachment>
</cac:FiscalLegislationDocumentReference>
```

```json
{
  "tender": {
    "documents": [
      {
        "id": "Fiscal1",
        "url": "https://fiscal-legislation.gov.stat"
      }
    ]
  }
}
```

</td>
      </tr>
      <tr id="OPT-111-Lot-FiscalLegis">
        <td class="field break-all">
            <p><b>OPT-111-Lot-FiscalLegis</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/parties.html#_legislation_information_provider"></a><br>Fiscal Legislation Document ID</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='Lot']/cac:TenderingTerms/cac:FiscalLegislationDocumentReference/cbc:ID</span></code>
        </td>
        <td class="mapping">

<a href="operations.md#get-the-document-for-a-document-reference">Get the document for the document reference</a>.

Set the document's `.documentType` to 'legislation'.

<a href="operations.md#get-the-lot-for-a-procurementprojectlot">Get the lot for the ProcurementProjectLot</a> and add its `id` to the document's `.relatedLots`.

```xml
<cac:ProcurementProjectLot>
  <cbc:ID schemeName="Lot">LOT-0001</cbc:ID>
  <cac:TenderingTerms>
    <cac:FiscalLegislationDocumentReference>
      <cbc:ID>Fiscal1</cbc:ID>
      <cac:Attachment>
        <cac:ExternalReference>
          <cbc:URI>https://fiscal-legislation.gov.stat</cbc:URI>
        </cac:ExternalReference>
      </cac:Attachment>
    </cac:FiscalLegislationDocumentReference>
  </cac:TenderingTerms>
</cac:ProcurementProjectLot>
```

```json
{
  "tender": {
    "documents": [
      {
        "id": "Fiscal1",
        "documentType": "legislation",
        "relatedLots": [
          "LOT-0001"
        ]
      }
    ]
  }
}
```

</td>
      </tr>
      <tr id="OPT-111-Part-FiscalLegis">
        <td class="field break-all">
            <p><b>OPT-111-Part-FiscalLegis</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/parties.html#_legislation_information_provider"></a><br>Fiscal Legislation Document ID</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='Part']/cac:TenderingTerms/cac:FiscalLegislationDocumentReference/cbc:ID</span></code>
        </td>
        <td class="mapping">

<a href="operations.md#get-the-document-for-a-document-reference">Get the document for the document reference</a>.

Set the document's `.documentType` to 'legislation'.

```xml
<cac:FiscalLegislationDocumentReference>
  <cbc:ID>Fiscal1</cbc:ID>
  <cac:Attachment>
    <cac:ExternalReference>
      <cbc:URI>https://fiscal-legislation.gov.stat</cbc:URI>
    </cac:ExternalReference>
  </cac:Attachment>
</cac:FiscalLegislationDocumentReference>
```

```json
{
  "tender": {
    "documents": [
      {
        "id": "Fiscal1",
        "documentType": "legislation"
      }
    ]
  }
}
```

</td>
      </tr>
      <tr id="OPT-112-Lot-EnvironLegis">
        <td class="field break-all">
            <p><b>OPT-112-Lot-EnvironLegis</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/parties.html#_legislation_information_provider"></a><br>Environmental Legislation Document ID</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='Lot']/cac:TenderingTerms/cac:EnvironmentalLegislationDocumentReference/cbc:ID</span></code>
        </td>
        <td class="mapping">

<a href="operations.md#get-the-document-for-a-document-reference">Get the document for the document reference</a>.

Set the document's `.documentType` to 'legislation'.

<a href="operations.md#get-the-lot-for-a-procurementprojectlot">Get the lot for the ProcurementProjectLot</a> and add its `id` to the document's `.relatedLots`.

```xml
<cac:ProcurementProjectLot>
  <cbc:ID schemeName="Lot">LOT-0001</cbc:ID>
  <cac:TenderingTerms>
    <cac:EnvironmentalLegislationDocumentReference>
      <cbc:ID>Env1</cbc:ID>
    </cac:EnvironmentalLegislationDocumentReference>
  </cac:TenderingTerms>
</cac:ProcurementProjectLot>
```

```json
{
  "tender": {
    "documents": [
      {
        "id": "Env1",
        "documentType": "legislation",
        "relatedLots": [
          "LOT-0001"
        ]
      }
    ]
  }
}
```

</td>
      </tr>
      <tr id="OPT-112-Part-EnvironLegis">
        <td class="field break-all">
            <p><b>OPT-112-Part-EnvironLegis</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/parties.html#_legislation_information_provider"></a><br>Environmental Legislation Document ID</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='Part']/cac:TenderingTerms/cac:EnvironmentalLegislationDocumentReference/cbc:ID</span></code>
        </td>
        <td class="mapping">

<a href="operations.md#get-the-document-for-a-document-reference">Get the document for the document reference</a>.

Set the document's `.documentType` to 'legislation'.

```xml
<cac:EnvironmentalLegislationDocumentReference>
  <cbc:ID>Env1</cbc:ID>
</cac:EnvironmentalLegislationDocumentReference>
```

```json
{
  "tender": {
    "documents": [
      {
        "id": "Env1",
        "documentType": "legislation"
      }
    ]
  }
}
```

</td>
      </tr>
      <tr id="OPT-113-Lot-EmployLegis">
        <td class="field break-all">
            <p><b>OPT-113-Lot-EmployLegis</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/parties.html#_legislation_information_provider"></a><br>Employment Legislation Document ID</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='Lot']/cac:TenderingTerms/cac:EmploymentLegislationDocumentReference/cbc:ID</span></code>
        </td>
        <td class="mapping">

<a href="operations.md#get-the-document-for-a-document-reference">Get the document for the document reference</a>.

Set the document's `.documentType` to 'legislation'.

<a href="operations.md#get-the-lot-for-a-procurementprojectlot">Get the lot for the ProcurementProjectLot</a> and add its `id` to the document's `.relatedLots`.

```xml
<cac:ProcurementProjectLot>
  <cbc:ID schemeName="Lot">LOT-0001</cbc:ID>
  <cac:TenderingTerms>
    <cac:EmploymentLegislationDocumentReference>
      <cbc:ID>Empl1</cbc:ID>
    </cac:EmploymentLegislationDocumentReference>
  </cac:TenderingTerms>
</cac:ProcurementProjectLot>
```

```json
{
  "tender": {
    "documents": [
      {
        "id": "Empl1",
        "documentType": "legislation",
        "relatedLots": [
          "LOT-0001"
        ]
      }
    ]
  }
}
```

</td>
      </tr>
      <tr id="OPT-113-Part-EmployLegis">
        <td class="field break-all">
            <p><b>OPT-113-Part-EmployLegis</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/parties.html#_legislation_information_provider"></a><br>Employment Legislation Document ID</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='Part']/cac:TenderingTerms/cac:EmploymentLegislationDocumentReference/cbc:ID</span></code>
        </td>
        <td class="mapping">

<a href="operations.md#get-the-document-for-a-document-reference">Get the document for the document reference</a>.

Set the document's `.documentType` to 'legislation'.

```xml
<cac:EmploymentLegislationDocumentReference>
  <cbc:ID>Empl1</cbc:ID>
</cac:EmploymentLegislationDocumentReference>
```

```json
{
  "tender": {
    "documents": [
      {
        "id": "Empl1",
        "documentType": "legislation"
      }
    ]
  }
}
```

</td>
      </tr>
      <tr id="OPT-120-Lot-EnvironLegis">
        <td class="field break-all">
            <p><b>OPT-120-Lot-EnvironLegis</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/parties.html#_legislation_information_provider"></a><br>URL to Environmental Legislation</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='Lot']/cac:TenderingTerms/cac:EnvironmentalLegislationDocumentReference/cac:Attachment/cac:ExternalReference/cbc:URI</span></code>
        </td>
        <td class="mapping">

<a href="operations.md#get-the-document-for-a-document-reference">Get the document for the document reference</a>.

Map to the document's `.url`.

<a href="operations.md#get-the-lot-for-a-procurementprojectlot">Get the lot for the ProcurementProjectLot</a> and add its `id` to the document's `.relatedLots`.

```xml
<cac:ProcurementProjectLot>
  <cbc:ID schemeName="Lot">LOT-0001</cbc:ID>
  <cac:TenderingTerms>
    <cac:EnvironmentalLegislationDocumentReference>
      <cbc:ID>Env1</cbc:ID>
      <cac:Attachment>
        <cac:ExternalReference>
          <cbc:URI>http://environmental-legislation.gov.stat</cbc:URI>
        </cac:ExternalReference>
      </cac:Attachment>
    </cac:EnvironmentalLegislationDocumentReference>
  </cac:TenderingTerms>
</cac:ProcurementProjectLot>
```

```json
{
  "tender": {
    "documents": [
      {
        "id": "Env1",
        "url": "https://environmental-legislation.gov.stat",
        "relatedLots": [
          "LOT-0001"
        ]
      }
    ]
  }
}
```

</td>
      </tr>
      <tr id="OPT-120-Part-EnvironLegis">
        <td class="field break-all">
            <p><b>OPT-120-Part-EnvironLegis</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/parties.html#_legislation_information_provider"></a><br>URL to Environmental Legislation</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='Part']/cac:TenderingTerms/cac:EnvironmentalLegislationDocumentReference/cac:Attachment/cac:ExternalReference/cbc:URI</span></code>
        </td>
        <td class="mapping">

<a href="operations.md#get-the-document-for-a-document-reference">Get the document for the document reference</a>.

Map to the document's `.url`.

```xml
<cac:EnvironmentalLegislationDocumentReference>
  <cbc:ID>Env1</cbc:ID>
  <cac:Attachment>
    <cac:ExternalReference>
      <cbc:URI>http://environmental-legislation.gov.stat</cbc:URI>
    </cac:ExternalReference>
  </cac:Attachment>
</cac:EnvironmentalLegislationDocumentReference>
```

```json
{
  "tender": {
    "documents": [
      {
        "id": "Env1",
        "url": "https://environmental-legislation.gov.stat"
      }
    ]
  }
}
```

</td>
      </tr>
      <tr id="OPT-130-Lot-EmployLegis">
        <td class="field break-all">
            <p><b>OPT-130-Lot-EmployLegis</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/parties.html#_legislation_information_provider"></a><br>URL to Employment Legislation</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='Lot']/cac:TenderingTerms/cac:EmploymentLegislationDocumentReference/cac:Attachment/cac:ExternalReference/cbc:URI</span></code>
        </td>
        <td class="mapping">

<a href="operations.md#get-the-document-for-a-document-reference">Get the document for the document reference</a>.

Map to the document's `.url`.

<a href="operations.md#get-the-lot-for-a-procurementprojectlot">Get the lot for the ProcurementProjectLot</a> and add its `id` to the document's `.relatedLots`.

```xml
<cac:ProcurementProjectLot>
  <cbc:ID schemeName="Lot">LOT-0001</cbc:ID>
  <cac:TenderingTerms>
    <cac:EmploymentLegislationDocumentReference>
      <cbc:ID>Empl1</cbc:ID>
      <cac:Attachment>
        <cac:ExternalReference>
          <cbc:URI>http://employment-legislation.gov.stat</cbc:URI>
        </cac:ExternalReference>
      </cac:Attachment>
    </cac:EmploymentLegislationDocumentReference>
  </cac:TenderingTerms>
</cac:ProcurementProjectLot>
```

```json
{
  "tender": {
    "documents": [
      {
        "id": "Empl1",
        "url": "https://employment-legislation.gov.stat",
        "relatedLots": [
          "LOT-0001"
        ]
      }
    ]
  }
}
```

</td>
      </tr>
      <tr id="OPT-130-Part-EmployLegis">
        <td class="field break-all">
            <p><b>OPT-130-Part-EmployLegis</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/parties.html#_legislation_information_provider"></a><br>URL to Employment Legislation</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='Part']/cac:TenderingTerms/cac:EmploymentLegislationDocumentReference/cac:Attachment/cac:ExternalReference/cbc:URI</span></code>
        </td>
        <td class="mapping">

<a href="operations.md#get-the-document-for-a-document-reference">Get the document for the document reference</a>.

Map to the document's `.url`.

```xml
<cac:EmploymentLegislationDocumentReference>
  <cbc:ID>Empl1</cbc:ID>
  <cac:Attachment>
    <cac:ExternalReference>
      <cbc:URI>http://employment-legislation.gov.stat</cbc:URI>
    </cac:ExternalReference>
  </cac:Attachment>
</cac:EmploymentLegislationDocumentReference>
```

```json
{
  "tender": {
    "documents": [
      {
        "id": "Empl1",
        "url": "https://employment-legislation.gov.stat"
      }
    ]
  }
}
```

</td>
      </tr>
      <tr id="OPT-140-Lot">
        <td class="field break-all">
            <p><b>OPT-140-Lot</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/procedure-lot-part-information.html#procurementDocsSection"></a><br>Procurement Documents ID</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='Lot']/cac:TenderingTerms/cac:CallForTendersDocumentReference/cbc:ID</span></code>
        </td>
        <td class="mapping">

<a href="operations.md#get-the-document-for-a-document-reference">Get the document for the document reference</a>.

<a href="operations.md#get-the-lot-for-a-procurementprojectlot">Get the lot for the ProcurementProjectLot</a> and add its `id` to the document's `.relatedLots`.

```xml
<cac:CallForTendersDocumentReference>
  <cbc:ID>20210521/CTFD/ENG/7654-02</cbc:ID>
</cac:CallForTendersDocumentReference>
```

```json
{
  "tender": {
    "documents": [
      {
        "id": "20210521/CTFD/ENG/7654-02",
        "relatedLots": [
          "LOT-0001"
        ]
      }
    ]
  }
}
```

</td>
      </tr>
      <tr id="OPT-140-Part">
        <td class="field break-all">
            <p><b>OPT-140-Part</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/procedure-lot-part-information.html#procurementDocsSection"></a><br>Procurement Documents ID</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='Part']/cac:TenderingTerms/cac:CallForTendersDocumentReference/cbc:ID</span></code>
        </td>
        <td class="mapping">

<a href="operations.md#get-the-document-for-a-document-reference">Get the document for the document reference</a>.

```xml
<cac:CallForTendersDocumentReference>
  <cbc:ID>20210521/CTFD/ENG/7654-02</cbc:ID>
</cac:CallForTendersDocumentReference>
```

```json
{
  "tender": {
    "documents": [
      {
        "id": "20210521/CTFD/ENG/7654-02"
      }
    ]
  }
}
```

</td>
      </tr>
      <tr id="OPT-150-Lot">
        <td class="field break-all">
            <p><b>OPT-150-Lot</b> <br>Subcontracting Allowed</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='Lot']/cac:TenderingTerms/cac:AllowedSubcontractTerms[cbc:SubcontractingConditionsCode/@listName='subcontracting-allowed']/cbc:SubcontractingConditionsCode</span></code>
        </td>
        <td class="mapping">

This data element is underspecified in eForms. No mapping is available.





</td>
      </tr>
      <tr id="OPT-155-LotResult">
        <td class="field break-all">
            <p><b>OPT-155-LotResult</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/competition-results.html#_lot_result"></a><br>Vehicle Type</p>
            <code class="docutils literal notranslate"><span class="pre">/*/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:NoticeResult/efac:LotResult/efac:StrategicProcurement/efac:StrategicProcurementInformation/efac:ProcurementDetails/efac:StrategicProcurementStatistics/efbc:StatisticsCode</span></code>
        </td>
        <td class="mapping">

This field maps to the same `Item` objects as created for BT-723-LotResult, BT-735-LotResult and OPT-156-LotResult.

If the value of `ancestor::efac:StrategicProcurementStatistics/efbc:StatisticsNumeric` is 0 discard. Otherwise:
\- <a href="operations.md#get-the-award-for-a-lotresult">Get the award for the LotResult</a>
\- Add an `Item` object to its `items` array.
\- Set the item's `.id` incrementally.

For each `efbc:StatisticsCode` add a `Classification` object to the item's `additionalClassifications` array.
\- Set the classification's `.scheme` to "vehicles".
\- Map the value of the field to the classification's `.id`.
\- Look up the code's label in the <a href="https://op.europa.eu/en/web/eu-vocabularies/concept-scheme/-/resource?uri=http://publications.europa.eu/resource/authority/vehicles">authority table</a> and map it to the classification's `.description`.

```xml
<efac:StrategicProcurementStatistics>
  <efbc:StatisticsCode listName="vehicles">vehicles-zero-emission</efbc:StatisticsCode>
</efac:StrategicProcurementStatistics>
```

```json
{
  "awards": [
    {
      "items": [
        {
          "id": "1",
          "additionalClassifications": [
            {
              "scheme": "vehicles",
              "id": "vehicles-zero-emission",
              "description": "vehicles zero emission"
            }
          ]
        }
      ]
    }
  ]
}
```

</td>
      </tr>
      <tr id="OPT-156-LotResult">
        <td class="field break-all">
            <p><b>OPT-156-LotResult</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/competition-results.html#_lot_result"></a><br>Vehicle Numeric</p>
            <code class="docutils literal notranslate"><span class="pre">/*/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:NoticeResult/efac:LotResult/efac:StrategicProcurement/efac:StrategicProcurementInformation/efac:ProcurementDetails/efac:StrategicProcurementStatistics/efbc:StatisticsNumeric</span></code>
        </td>
        <td class="mapping">

This field maps to the same `Item` objects as created for BT-723-LotResult, BT-735-LotResult and OPT-155-LotResult.

If the value of this field is 0 then discard. Otherwise:

- If the value of the `ancestor::efbc:StrategicProcurementStatistics/efbc:StatisticsCode` is "vehicles-zero-emissions" or "vehicles-clean", get the corresponding item and map to it's `.quantity`.
- If the value of `ancestor::efbc:StrategicProcurementStatistics/efbc:StatisticsCode` is "vehicles", get the value of `efbc:StatisticsNumeric` for each `ancestor::efbc:StrategicProcurementStatistics` with `efbc:StatisticsCode` equal to "vehicles-zero-emissions" or "vehicles-clean" and subtract the sum of the values from the value of this field.
- If the value is 0 discard the item entirely. Otherwise map the the result to the item's `.quantity`.

```xml
<efac:StrategicProcurementStatistics>
  <efbc:StatisticsNumeric>0</efbc:StatisticsNumeric>
</efac:StrategicProcurementStatistics>
```

```json
{
  "awards": [
    {
      "items": [
        {
          "id": "1",
          "quantity": 3
        }
      ]
    }
  ]
}
```

</td>
      </tr>
      <tr id="OPT-160-UBO">
        <td class="field break-all">
            <p><b>OPT-160-UBO</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/parties.html#ultimateBeneficialOwnerSection"></a><br>First Name</p>
            <code class="docutils literal notranslate"><span class="pre">/*/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:Organizations/efac:UltimateBeneficialOwner/cbc:FirstName</span></code>
        </td>
        <td class="mapping">

<a href="operations.md#get-the-person-for-an-ultimate-beneficial-owner">Get the person for the ultimate beneficial owner</a> and map to the person's `.name`.

```xml
<efac:UltimateBeneficialOwner>
  <cbc:FirstName>Mickey</cbc:FirstName>
</efac:UltimateBeneficialOwner>
```

```json
{
  "parties": [
    {
      "beneficialOwners": [
        {
          "name": "Mickey"
        }
      ]
    }
  ]
}
```

</td>
      </tr>
      <tr id="OPT-170-Tenderer">
        <td class="field break-all">
            <p><b>OPT-170-Tenderer</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/competition-results.html#tenderingPartySection"></a><br>Tendering Party Leader</p>
            <code class="docutils literal notranslate"><span class="pre">/*/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:NoticeResult/efac:TenderingParty/efac:Tenderer/efbc:GroupLeadIndicator</span></code>
        </td>
        <td class="mapping">

<a href="operations.md#get-the-organization-for-a-tenderer">Get the organization for the tenderer</a>. If "true", add 'leadTenderer' to its `.roles`.

```xml
<efac:Tenderer>
  <efbc:GroupLeadIndicator>true</efbc:GroupLeadIndicator>
</efac:Tenderer>
```

```json
{
  "parties": [
    {
      "id": "ORG-0001",
      "roles": [
        "leadTenderer",
        "tenderer"
      ]
    }
  ]
}
```

</td>
      </tr>
      <tr id="OPT-200-Organization-Company">
        <td class="field break-all">
            <p><b>OPT-200-Organization-Company</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/parties.html#_general_structure_of_an_organization_related_information"></a><br>Organisation Technical Identifier</p>
            <code class="docutils literal notranslate"><span class="pre">/*/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:Organizations/efac:Organization/efac:Company/cac:PartyIdentification/cbc:ID</span></code>
        </td>
        <td class="mapping">

If there is an `Organization` in `parties` whose `.id` is equal to the value of this field, discard. Otherwise, add an `Organization` to `parties` and map to its `.id`.

```xml
<efac:Organization>
  <efac:Company>
    <cac:PartyIdentification>
      <cbc:ID schemeName="organization">ORG-0001</cbc:ID>
    </cac:PartyIdentification>
  </efac:Company>
</efac:Organization>
```

```json
{
  "parties": [
    {
      "id": "ORG-0001"
    }
  ]
}
```

</td>
      </tr>
      <tr id="OPT-201-Organization-TouchPoint">
        <td class="field break-all">
            <p><b>OPT-201-Organization-TouchPoint</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/parties.html#_general_structure_of_an_organization_related_information"></a><br>TouchPoint Technical Identifier</p>
            <code class="docutils literal notranslate"><span class="pre">/*/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:Organizations/efac:Organization/efac:TouchPoint/cac:PartyIdentification/cbc:ID</span></code>
        </td>
        <td class="mapping">

If there is an `Organization` in `parties` whose `.id` is equal to the value of this field, discard. Otherwise, add an `Organization` to `parties` and map to its `.id`.

```xml
<efac:Organization>
  <efac:TouchPoint>
    <cac:PartyIdentification>
      <cbc:ID schemeName="touchpoint">TPO-0001</cbc:ID>
    </cac:PartyIdentification>
  </efac:TouchPoint>
</efac:Organization>
```

```json
{
  "parties": [
    {
      "id": "TPO-0001"
    }
  ]
}
```

</td>
      </tr>
      <tr id="OPT-202-UBO">
        <td class="field break-all">
            <p><b>OPT-202-UBO</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/parties.html#ultimateBeneficialOwnerSection"></a><br>Beneficial Owner Technical Identifier</p>
            <code class="docutils literal notranslate"><span class="pre">/*/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:Organizations/efac:UltimateBeneficialOwner/cbc:ID</span></code>
        </td>
        <td class="mapping">

<a href="operations.md#get-the-person-for-an-ultimate-beneficial-owner">Get the person for the ultimate beneficial owner</a> and map to the person's `.id`.

```xml
<efac:UltimateBeneficialOwner>
  <cbc:ID schemeName="ubo">UBO-0001</cbc:ID>
</efac:UltimateBeneficialOwner>
```

```json
{
  "parties": [
    {
      "beneficialOwners": [
        {
          "id": "UBO-0001"
        }
      ]
    }
  ]
}
```

</td>
      </tr>
      <tr id="OPT-210-Tenderer">
        <td class="field break-all">
            <p><b>OPT-210-Tenderer</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/competition-results.html#tenderingPartySection"></a><br>Tendering Party ID</p>
            <code class="docutils literal notranslate"><span class="pre">/*/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:NoticeResult/efac:TenderingParty/cbc:ID</span></code>
        </td>
        <td class="mapping">

Discard. Each tenderer in the tendering party is covered by OPT-310-Tenderer.

```xml
<efac:TenderingParty>
  <cbc:ID schemeName="tendering-party">TPA-0003</cbc:ID>
</efac:TenderingParty>
```



</td>
      </tr>
      <tr id="OPT-300-Contract-Signatory">
        <td class="field break-all">
            <p><b>OPT-300-Contract-Signatory</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/parties.html#_contract_signatory"></a><br>Signatory Identifier Reference</p>
            <code class="docutils literal notranslate"><span class="pre">/*/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:NoticeResult/efac:SettledContract/cac:SignatoryParty/cac:PartyIdentification/cbc:ID</span></code>
        </td>
        <td class="mapping">

- Get the `Organization` in `parties` whose `.id` is equal to the value of this field. If none exists yet:
  - Add an `Organization` to `parties`.
  - Set its `.id` to the value of this field.
- Add 'buyer' to its roles.
- Get the `ancestor::efext:EformsExtension/efac:Organizations/efac:Organization/efac:Company` whose `/cac:PartyIdentification/cbc:ID` is equal to the value of this field and set the organization's `.name` to the value of `/cac:PartyName/cbc:Name`.
- <a href="operations.md#get-the-contract-for-a-settledcontract">Get the contract for the SettledContract</a>. For each award referenced in the contract's `.awardID` field or `.awardIDs` array:
  - Add an `OrganizationReference` object to the award's `.buyers` array.
  - Set its `.id` to the organization's `.id`.

```xml
<efac:SettledContract>
  <cac:SignatoryParty>
    <cbc:ID schemeName="organization">ORG-0001</cbc:ID>
  </cac:SignatoryParty>
</efac:SettledContract>
```

```json
{
  "awards": [
    {
      "buyers": [
        {
          "id": "ORG-0001",
          "name": "Financial Adinistration for ..."
        }
      ]
    }
  ]
}
```

</td>
      </tr>
      <tr id="OPT-300-Procedure-Buyer">
        <td class="field break-all">
            <p><b>OPT-300-Procedure-Buyer</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/identifiers.html#_referring_to_objects"></a><br>Buyer Technical Identifier Reference</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ContractingParty/cac:Party/cac:PartyIdentification/cbc:ID</span></code>
        </td>
        <td class="mapping">

<a href="operations.md#get-the-organization-for-an-organization-technical-identifier-reference">Get the organization for the organization technical identifier reference</a>

- Add 'buyer' to its `.roles` array.
- Add an `OrganizationReference` object to `buyer` and set its `.id` to the organization's `.id`.

```xml
<cac:PartyIdentification>
  <cbc:ID schemeName="organization">ORG-0001</cbc:ID>
</cac:PartyIdentification>
```

```json
{
  "parties": [
    {
      "id": "ORG-0001",
      "roles": [
        "buyer"
      ]
    }
  ],
  "buyer": {
    "id": "ORG-0001",
    "name": "Financial Administration for ..."
  }
}
```

</td>
      </tr>
      <tr id="OPT-300-Procedure-SProvider">
        <td class="field break-all">
            <p><b>OPT-300-Procedure-SProvider</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/identifiers.html#_referring_to_objects"></a><br>Service Provider Technical Identifier Reference</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ContractingParty/cac:Party/cac:ServiceProviderParty/cac:Party/cac:PartyIdentification/cbc:ID</span></code>
        </td>
        <td class="mapping">

<a href="operations.md#get-the-organization-for-an-organization-technical-identifier-reference">Get the organization for the organization technical identifier reference</a>.

Get the `ancestor::efext:EformsExtension/efac:Organizations/efac:Organization/efac:Company` whose `/cac:PartyIdentification/cbc:ID` is equal to the value of this field and set the organization's `.name` to the value of `/cac:PartyName/cbc:Name`.

```xml
<cac:PartyIdentification>
  <cbc:ID schemeName="organization">ORG-0001</cbc:ID>
</cac:PartyIdentification>
```

```json
{
  "parties": [
    {
      "id": "ORG-0001",
      "name": "Service Provider Ltd"
    }
  ]
}
```

</td>
      </tr>
      <tr id="OPT-300-Tenderer">
        <td class="field break-all">
            <p><b>OPT-300-Tenderer</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/competition-results.html#tenderingPartySection"></a><br>Tenderer ID Reference</p>
            <code class="docutils literal notranslate"><span class="pre">/*/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:NoticeResult/efac:TenderingParty/efac:Tenderer/cbc:ID</span></code>
        </td>
        <td class="mapping">

Discard. This field is mapped as part of OPT-310-Tender.

```xml
<efac:Tenderer>
  <cbc:ID schemeName="organization">ORG-0005</cbc:ID>
</efac:Tenderer>
```



</td>
      </tr>
      <tr id="OPT-301-Lot-AddInfo">
        <td class="field break-all">
            <p><b>OPT-301-Lot-AddInfo</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/procedure-lot-part-information.html#partiesSection"></a><br>Additional Info Provider Technical Identifier Reference</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='Lot']/cac:TenderingTerms/cac:AdditionalInformationParty/cac:PartyIdentification/cbc:ID</span></code>
        </td>
        <td class="mapping">

<a href="operations.md#get-the-organization-for-an-organization-technical-identifier-reference">Get the organization for the organization technical identifier reference</a> and add 'processContactPoint' to its `.roles` array.

eForms allows additional information providers to differ per lot. However, while this may be permitted by law, we have found no evidence in practice. Please contact data@open-contracting.org if you have a use case.

```xml
<cac:ProcurementProjectLot>
  <cac:TenderingTerms>
    <cac:AdditionalInformationParty>
      <cac:PartyIdentification>
        <cbc:ID schemeName="touchpoint">TPO-0001</cbc:ID>
      </cac:PartyIdentification>
    </cac:AdditionalInformationParty>
  </cac:TenderingTerms>
</cac:ProcurementProjectLot>
```

```json
{
  "parties": [
    {
      "id": "TPO-0001",
      "roles": [
        "processContactPoint"
      ]
    }
  ]
}
```

</td>
      </tr>
      <tr id="OPT-301-Lot-DocProvider">
        <td class="field break-all">
            <p><b>OPT-301-Lot-DocProvider</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/parties.html#_sub_roles"></a><br>Document Provider Technical Identifier Reference</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='Lot']/cac:TenderingTerms/cac:DocumentProviderParty/cac:PartyIdentification/cbc:ID</span></code>
        </td>
        <td class="mapping">

<a href="operations.md#get-the-organization-for-an-organization-technical-identifier-reference">Get the organization for the organization technical identifier reference</a> and add 'processContactPoint' to its `.roles` array.

eForms allows document providers to differ per lot. However, while this may be permitted by law, we have found no evidence in practice. Please contact data@open-contracting.org if you have a use case.

```xml
<cac:ProcurementProjectLot>
  <cac:TenderingTerms>
    <cac:DocumentProviderParty>
      <cac:PartyIdentification>
        <cbc:ID schemeName="touchpoint">TPO-0001</cbc:ID>
      </cac:PartyIdentification>
    </cac:DocumentProviderParty>
  </cac:TenderingTerms>
</cac:ProcurementProjectLot>
```

```json
{
  "parties": [
    {
      "id": "TPO-0001",
      "roles": [
        "offlineDocumentProvider"
      ]
    }
  ]
}
```

</td>
      </tr>
      <tr id="OPT-301-Lot-EmployLegis">
        <td class="field break-all">
            <p><b>OPT-301-Lot-EmployLegis</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/competition-results.html#tenderingPartySection"></a><br>Employment Legislation Organization Technical Identifier Reference</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='Lot']/cac:TenderingTerms/cac:EmploymentLegislationDocumentReference/cac:IssuerParty/cac:PartyIdentification/cbc:ID</span></code>
        </td>
        <td class="mapping">

<a href="operations.md#get-the-document-for-a-document-reference">Get the document for the document reference</a> and map to its `publisher.id`.

<a href="operations.md#get-the-lot-for-a-procurementprojectlot">Get the lot for the ProcurementProjectLot</a> and add its `id` to the document's `.relatedLots`.

<a href="operations.md#get-the-organization-for-an-organization-technical-identifier-reference">Get the organization for the organization technical identifier reference</a> and add 'informationProvider' to is `roles` array.

```xml
<ext:UBLExtensions>
  <ext:UBLExtension>
    <ext:ExtensionContent>
      <efext:EformsExtension>
        <efac:Organizations>
          <efac:Organization>
            <efac:Company>
              <cac:PartyIdentification>
                <cbc:ID schemeName="organization">ORG-0001</cbc:ID>
              </cac:PartyIdentification>
            </efac:Company>
          </efac:Organization>
        </efac:Organizations>
      </efext:EformsExtension>
    </ext:ExtensionContent>
  </ext:UBLExtension>
</ext:UBLExtensions>
<cac:ProcurementProjectLot>
  <cbc:ID schemeName="Lot">LOT-0001</cbc:ID>
  <cac:TenderingTerms>
    <cac:EmploymentLegislationDocumentReference>
      <cbc:ID>Empl1</cbc:ID>
      <cac:IssuerParty>
        <cac:PartyIdentification>
          <cbc:ID schemeName="organization">ORG-0001</cbc:ID>
        </cac:PartyIdentification>
      </cac:IssuerParty>
    </cac:EmploymentLegislationDocumentReference>
  </cac:TenderingTerms>
</cac:ProcurementProjectLot>
```

```json
{
  "parties": [
    {
      "id": "ORG-0001",
      "roles": [
        "informationProvider"
      ]
    }
  ],
  "tender": {
    "documents": [
      {
        "id": "Empl1",
        "publisher": {
          "id": "ORG-0001"
        },
        "relatedLots": [
          "LOT-0001"
        ]
      }
    ]
  }
}
```

</td>
      </tr>
      <tr id="OPT-301-Lot-EnvironLegis">
        <td class="field break-all">
            <p><b>OPT-301-Lot-EnvironLegis</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/competition-results.html#tenderingPartySection"></a><br>Environmental Legislation Organization Technical Identifier Reference</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='Lot']/cac:TenderingTerms/cac:EnvironmentalLegislationDocumentReference/cac:IssuerParty/cac:PartyIdentification/cbc:ID</span></code>
        </td>
        <td class="mapping">

<a href="operations.md#get-the-document-for-a-document-reference">Get the document for the document reference</a> and map to its `publisher.id`.

<a href="operations.md#get-the-lot-for-a-procurementprojectlot">Get the lot for the ProcurementProjectLot</a> and add its `id` to the document's `.relatedLots`.

<a href="operations.md#get-the-organization-for-an-organization-technical-identifier-reference">Get the organization for the organization technical identifier reference</a> and add 'informationProvider' to is `roles` array.

```xml
<ext:UBLExtensions>
  <ext:UBLExtension>
    <ext:ExtensionContent>
      <efext:EformsExtension>
        <efac:Organizations>
          <efac:Organization>
            <efac:Company>
              <cac:PartyIdentification>
                <cbc:ID schemeName="organization">ORG-0001</cbc:ID>
              </cac:PartyIdentification>
            </efac:Company>
          </efac:Organization>
        </efac:Organizations>
      </efext:EformsExtension>
    </ext:ExtensionContent>
  </ext:UBLExtension>
</ext:UBLExtensions>
<cac:ProcurementProjectLot>
  <cbc:ID schemeName="Lot">LOT-0001</cbc:ID>
  <cac:TenderingTerms>
    <cac:EnvironmentalLegislationDocumentReference>
      <cbc:ID>Env1</cbc:ID>
      <cac:IssuerParty>
        <cac:PartyIdentification>
          <cbc:ID schemeName="organization">ORG-0001</cbc:ID>
        </cac:PartyIdentification>
      </cac:IssuerParty>
    </cac:EnvironmentalLegislationDocumentReference>
  </cac:TenderingTerms>
</cac:ProcurementProjectLot>
```

```json
{
  "parties": [
    {
      "id": "ORG-0001",
      "roles": [
        "informationProvider"
      ]
    }
  ],
  "tender": {
    "documents": [
      {
        "id": "Env1",
        "publisher": {
          "id": "ORG-0001"
        },
        "relatedLots": [
          "LOT-0001"
        ]
      }
    ]
  }
}
```

</td>
      </tr>
      <tr id="OPT-301-Lot-FiscalLegis">
        <td class="field break-all">
            <p><b>OPT-301-Lot-FiscalLegis</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/competition-results.html#tenderingPartySection"></a><br>Fiscal Legislation Organization Technical Identifier Reference</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='Lot']/cac:TenderingTerms/cac:FiscalLegislationDocumentReference/cac:IssuerParty/cac:PartyIdentification/cbc:ID</span></code>
        </td>
        <td class="mapping">

<a href="operations.md#get-the-document-for-a-document-reference">Get the document for the document reference</a> and map to its `publisher.id`.

<a href="operations.md#get-the-lot-for-a-procurementprojectlot">Get the lot for the ProcurementProjectLot</a> and add its `id` to the document's `.relatedLots`.

<a href="operations.md#get-the-organization-for-an-organization-technical-identifier-reference">Get the organization for the organization technical identifier reference</a> and add 'informationProvider' to is `roles` array.

```xml
<ext:UBLExtensions>
  <ext:UBLExtension>
    <ext:ExtensionContent>
      <efext:EformsExtension>
        <efac:Organizations>
          <efac:Organization>
            <efac:Company>
              <cac:PartyIdentification>
                <cbc:ID schemeName="organization">ORG-0001</cbc:ID>
              </cac:PartyIdentification>
            </efac:Company>
          </efac:Organization>
        </efac:Organizations>
      </efext:EformsExtension>
    </ext:ExtensionContent>
  </ext:UBLExtension>
</ext:UBLExtensions>
<cac:ProcurementProjectLot>
  <cbc:ID schemeName="Lot">LOT-0001</cbc:ID>
  <cac:TenderingTerms>
    <cac:FiscalLegislationDocumentReference>
      <cbc:ID>Fiscal1</cbc:ID>
      <cac:IssuerParty>
        <cac:PartyIdentification>
          <cbc:ID schemeName="organization">ORG-0001</cbc:ID>
        </cac:PartyIdentification>
      </cac:IssuerParty>
    </cac:FiscalLegislationDocumentReference>
  </cac:TenderingTerms>
</cac:ProcurementProjectLot>
```

```json
{
  "parties": [
    {
      "id": "ORG-0001",
      "roles": [
        "informationProvider"
      ]
    }
  ],
  "tender": {
    "documents": [
      {
        "id": "Fiscal1",
        "publisher": {
          "id": "ORG-0001"
        },
        "relatedLots": [
          "LOT-0001"
        ]
      }
    ]
  }
}
```

</td>
      </tr>
      <tr id="OPT-301-Lot-Mediator">
        <td class="field break-all">
            <p><b>OPT-301-Lot-Mediator</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/competition-results.html#tenderingPartySection"></a><br>Mediator Technical Identifier Reference</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='Lot']/cac:TenderingTerms/cac:AppealTerms/cac:MediationParty/cac:PartyIdentification/cbc:ID</span></code>
        </td>
        <td class="mapping">

<a href="operations.md#get-the-organization-for-an-organization-technical-identifier-reference">Get the organization for the organization technical identifier reference</a> and add 'mediationBody, to the organization's `.roles` array.

eForms allows review bodies and mediation bodies to differ per lot. However, while this may be permitted by law, we have found no evidence in practice. Please contact data@open-contracting.org if you have a use case.

```xml
<cac:MediationParty>
  <cac:PartyIdentification>
    <cbc:ID schemeName="touchpoint">TPO-0005</cbc:ID>
  </cac:PartyIdentification>
</cac:MediationParty>
```

```json
{
  "parties": [
    {
      "id": "TPO-0005",
      "roles": [
        "mediationBody"
      ]
    }
  ]
}
```

</td>
      </tr>
      <tr id="OPT-301-Lot-ReviewInfo">
        <td class="field break-all">
            <p><b>OPT-301-Lot-ReviewInfo</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/procedure-lot-part-information.html#appealTermsSection"></a><br>Review Info Provider Technical Identifier Reference</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='Lot']/cac:TenderingTerms/cac:AppealTerms/cac:AppealInformationParty/cac:PartyIdentification/cbc:ID</span></code>
        </td>
        <td class="mapping">

<a href="operations.md#get-the-organization-for-an-organization-technical-identifier-reference">Get the organization for the organization technical identifier reference</a> and add 'reviewContactPoint' to its `.roles` array.

eForms allows review information providers to differ per lot. However, while this may be permitted by law, we have found no evidence in practice. Please contact data@open-contracting.org if you have a use case.

```xml
<cac:ProcurementProjectLot>
  <cac:TenderingTerms>
    <cac:AppealTerms>
      <cac:AppealInformationParty>
        <cac:PartyIdentification>
          <cbc:ID schemeName="touchpoint">TPO-0001</cbc:ID>
        </cac:PartyIdentification>
      </cac:AppealInformationParty>
    </cac:AppealTerms>
  </cac:TenderingTerms>
</cac:ProcurementProjectLot>
```

```json
{
  "parties": [
    {
      "id": "TPO-0001",
      "roles": [
        "reviewContactPoint"
      ]
    }
  ]
}
```

</td>
      </tr>
      <tr id="OPT-301-Lot-ReviewOrg">
        <td class="field break-all">
            <p><b>OPT-301-Lot-ReviewOrg</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/competition-results.html#tenderingPartySection"></a><br>Review Organization Technical Identifier Reference</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='Lot']/cac:TenderingTerms/cac:AppealTerms/cac:AppealReceiverParty/cac:PartyIdentification/cbc:ID</span></code>
        </td>
        <td class="mapping">

<a href="operations.md#get-the-organization-for-an-organization-technical-identifier-reference">Get the organization for the organization technical identifier reference</a> and add 'reviewBody, to the organization's `.roles` array.

eForms allows review bodies and mediation bodies to differ per lot. However, while this may be permitted by law, we have found no evidence in practice. Please contact data@open-contracting.org if you have a use case.

```xml
<cac:AppealReceiverParty>
  <cac:PartyIdentification>
    <cbc:ID schemeName="touchpoint">TPO-0003</cbc:ID>
  </cac:PartyIdentification>
</cac:AppealReceiverParty>
```

```json
{
  "parties": [
    {
      "id": "TPO-0003",
      "roles": [
        "reviewBody"
      ]
    }
  ]
}
```

</td>
      </tr>
      <tr id="OPT-301-Lot-TenderEval">
        <td class="field break-all">
            <p><b>OPT-301-Lot-TenderEval</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/procedure-lot-part-information.html#partiesSection"></a><br>Tender Evaluator Technical Identifier Reference</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='Lot']/cac:TenderingTerms/cac:TenderEvaluationParty/cac:PartyIdentification/cbc:ID</span></code>
        </td>
        <td class="mapping">

<a href="operations.md#get-the-organization-for-an-organization-technical-identifier-reference">Get the organization for the organization technical identifier reference</a> and add 'evaluationBody' to its `.roles` array.

eForms allows tender evaluation organizations to differ per lot. However, while this may be permitted by law, we have found no evidence in practice. Please contact data@open-contracting.org if you have a use case.

```xml
<cac:ProcurementProjectLot>
  <cac:TenderingTerms>
    <cac:TenderEvaluationParty>
      <cac:PartyIdentification>
        <cbc:ID schemeName="touchpoint">TPO-0001</cbc:ID>
      </cac:PartyIdentification>
    </cac:TenderEvaluationParty>
  </cac:TenderingTerms>
</cac:ProcurementProjectLot>
```

```json
{
  "parties": [
    {
      "id": "TPO-0001",
      "roles": [
        "evaluationBody"
      ]
    }
  ]
}
```

</td>
      </tr>
      <tr id="OPT-301-Lot-TenderReceipt">
        <td class="field break-all">
            <p><b>OPT-301-Lot-TenderReceipt</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/procedure-lot-part-information.html#partiesSection"></a><br>Tender Recipient Technical Identifier Reference</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='Lot']/cac:TenderingTerms/cac:TenderRecipientParty/cac:PartyIdentification/cbc:ID</span></code>
        </td>
        <td class="mapping">

<a href="operations.md#get-the-organization-for-an-organization-technical-identifier-reference">Get the organization for the organization technical identifier reference</a> and add 'submissionReceiptBody' to its `.roles` array.

eForms allows tender recipient organizations to differ per lot. However, while this may be permitted by law, we have found no evidence in practice. Please contact data@open-contracting.org if you have a use case.

```xml
<cac:ProcurementProjectLot>
  <cac:TenderingTerms>
    <cac:TenderRecipientParty>
      <cac:PartyIdentification>
        <cbc:ID schemeName="touchpoint">TPO-0001</cbc:ID>
      </cac:PartyIdentification>
    </cac:TenderRecipientParty>
  </cac:TenderingTerms>
</cac:ProcurementProjectLot>
```

```json
{
  "parties": [
    {
      "id": "TPO-0001",
      "roles": [
        "submissionReceiptBody"
      ]
    }
  ]
}
```

</td>
      </tr>
      <tr id="OPT-301-LotResult-Financing">
        <td class="field break-all">
            <p><b>OPT-301-LotResult-Financing</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/competition-results.html#tenderingPartySection"></a><br>Financing Party (ID reference)</p>
            <code class="docutils literal notranslate"><span class="pre">/*/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:NoticeResult/efac:LotResult/cac:FinancingParty/cac:PartyIdentification/cbc:ID</span></code>
        </td>
        <td class="mapping">

<a href="operations.md#get-the-organization-for-an-organization-technical-identifier-reference">Get the organization for the organization technical identifier reference</a> and add 'funder' to its `.roles` array.

eForms allows financing and payer parties to differ per lot. However, while this may be permitted by law, we have found no evidence in practice. Please contact data@open-contracting.org if you have a use case.

```xml
<cac:FinancingParty>
  <cac:PartyIdentification>
    <cbc:ID schemeName="organization">ORG-0003</cbc:ID>
  </cac:PartyIdentification>
</cac:FinancingParty>
```

```json
{
  "parties": [
    {
      "id": "ORG-0003",
      "roles": [
        "funder"
      ]
    }
  ]
}
```

</td>
      </tr>
      <tr id="OPT-301-LotResult-Paying">
        <td class="field break-all">
            <p><b>OPT-301-LotResult-Paying</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/competition-results.html#tenderingPartySection"></a><br>Payer Party (ID reference)</p>
            <code class="docutils literal notranslate"><span class="pre">/*/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:NoticeResult/efac:LotResult/cac:PayerParty/cac:PartyIdentification/cbc:ID</span></code>
        </td>
        <td class="mapping">

<a href="operations.md#get-the-organization-for-an-organization-technical-identifier-reference">Get the organization for the organization technical identifier reference</a> and add 'payer' to its `.roles` array.

eForms allows financing and payer parties to differ per lot. However, while this may be permitted by law, we have found no evidence in practice. Please contact data@open-contracting.org if you have a use case.

```xml
<cac:PayerParty>
  <cac:PartyIdentification>
    <cbc:ID schemeName="organization">ORG-0001</cbc:ID>
  </cac:PartyIdentification>
</cac:PayerParty>
```

```json
{
  "parties": [
    {
      "id": "ORG-0001",
      "roles": [
        "payer"
      ]
    }
  ]
}
```

</td>
      </tr>
      <tr id="OPT-301-Part-AddInfo">
        <td class="field break-all">
            <p><b>OPT-301-Part-AddInfo</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/procedure-lot-part-information.html#partiesSection"></a><br>Additional Info Provider Technical Identifier Reference</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='Part']/cac:TenderingTerms/cac:AdditionalInformationParty/cac:PartyIdentification/cbc:ID</span></code>
        </td>
        <td class="mapping">

<a href="operations.md#get-the-organization-for-an-organization-technical-identifier-reference">Get the organization for the organization technical identifier reference</a> and add 'processContactPoint' to its `.roles` array.

```xml
<cac:ProcurementProjectLot>
  <cac:TenderingTerms>
    <cac:AdditionalInformationParty>
      <cac:PartyIdentification>
        <cbc:ID schemeName="touchpoint">TPO-0001</cbc:ID>
      </cac:PartyIdentification>
    </cac:AdditionalInformationParty>
  </cac:TenderingTerms>
</cac:ProcurementProjectLot>
```

```json
{
  "parties": [
    {
      "id": "TPO-0001",
      "roles": [
        "processContactPoint"
      ]
    }
  ]
}
```

</td>
      </tr>
      <tr id="OPT-301-Part-DocProvider">
        <td class="field break-all">
            <p><b>OPT-301-Part-DocProvider</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/parties.html#_sub_roles"></a><br>Document Provider Technical Identifier Reference</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='Part']/cac:TenderingTerms/cac:DocumentProviderParty/cac:PartyIdentification/cbc:ID</span></code>
        </td>
        <td class="mapping">

<a href="operations.md#get-the-organization-for-an-organization-technical-identifier-reference">Get the organization for the organization technical identifier reference</a> and add 'processContactPoint' to its `.roles` array.

```xml
<cac:ProcurementProjectLot>
  <cac:TenderingTerms>
    <cac:DocumentProviderParty>
      <cac:PartyIdentification>
        <cbc:ID schemeName="touchpoint">TPO-0001</cbc:ID>
      </cac:PartyIdentification>
    </cac:DocumentProviderParty>
  </cac:TenderingTerms>
</cac:ProcurementProjectLot>
```

```json
{
  "parties": [
    {
      "id": "TPO-0001",
      "roles": [
        "offlineDocumentProvider"
      ]
    }
  ]
}
```

</td>
      </tr>
      <tr id="OPT-301-Part-EmployLegis">
        <td class="field break-all">
            <p><b>OPT-301-Part-EmployLegis</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/competition-results.html#tenderingPartySection"></a><br>Employment Legislation Organization Technical Identifier Reference</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='Part']/cac:TenderingTerms/cac:EmploymentLegislationDocumentReference/cac:IssuerParty/cac:PartyIdentification/cbc:ID</span></code>
        </td>
        <td class="mapping">

<a href="operations.md#get-the-document-for-a-document-reference">Get the document for the document reference</a> and map to its `publisher.id`.

<a href="operations.md#get-the-organization-for-an-organization-technical-identifier-reference">Get the organization for the organization technical identifier reference</a> and add 'informationProvider' to is `roles` array.

```xml
<ext:UBLExtensions>
  <ext:UBLExtension>
    <ext:ExtensionContent>
      <efext:EformsExtension>
        <efac:Organizations>
          <efac:Organization>
            <efac:Company>
              <cac:PartyIdentification>
                <cbc:ID schemeName="organization">ORG-0001</cbc:ID>
              </cac:PartyIdentification>
            </efac:Company>
          </efac:Organization>
        </efac:Organizations>
      </efext:EformsExtension>
    </ext:ExtensionContent>
  </ext:UBLExtension>
</ext:UBLExtensions>
<cac:ProcurementProjectLot>
  <cac:TenderingTerms>
    <cac:EmploymentLegislationDocumentReference>
      <cbc:ID>Empl1</cbc:ID>
      <cac:IssuerParty>
        <cac:PartyIdentification>
          <cbc:ID schemeName="organization">ORG-0001</cbc:ID>
        </cac:PartyIdentification>
      </cac:IssuerParty>
    </cac:EmploymentLegislationDocumentReference>
  </cac:TenderingTerms>
</cac:ProcurementProjectLot>
```

```json
{
  "parties": [
    {
      "id": "ORG-0001",
      "roles": [
        "informationProvider"
      ]
    }
  ],
  "tender": {
    "documents": [
      {
        "id": "Empl1",
        "publisher": {
          "id": "ORG-0001"
        }
      }
    ]
  }
}
```

</td>
      </tr>
      <tr id="OPT-301-Part-EnvironLegis">
        <td class="field break-all">
            <p><b>OPT-301-Part-EnvironLegis</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/competition-results.html#tenderingPartySection"></a><br>Environmental Legislation Organization Technical Identifier Reference</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='Part']/cac:TenderingTerms/cac:EnvironmentalLegislationDocumentReference/cac:IssuerParty/cac:PartyIdentification/cbc:ID</span></code>
        </td>
        <td class="mapping">

<a href="operations.md#get-the-document-for-a-document-reference">Get the document for the document reference</a> and map to its `publisher.id`.

<a href="operations.md#get-the-organization-for-an-organization-technical-identifier-reference">Get the organization for the organization technical identifier reference</a> and add 'informationProvider' to is `roles` array.

```xml
<ext:UBLExtensions>
  <ext:UBLExtension>
    <ext:ExtensionContent>
      <efext:EformsExtension>
        <efac:Organizations>
          <efac:Organization>
            <efac:Company>
              <cac:PartyIdentification>
                <cbc:ID schemeName="organization">ORG-0001</cbc:ID>
              </cac:PartyIdentification>
            </efac:Company>
          </efac:Organization>
        </efac:Organizations>
      </efext:EformsExtension>
    </ext:ExtensionContent>
  </ext:UBLExtension>
</ext:UBLExtensions>
<cac:ProcurementProjectLot>
  <cac:TenderingTerms>
    <cac:EnvironmentalLegislationDocumentReference>
      <cbc:ID>Env1</cbc:ID>
      <cac:IssuerParty>
        <cac:PartyIdentification>
          <cbc:ID schemeName="organization">ORG-0001</cbc:ID>
        </cac:PartyIdentification>
      </cac:IssuerParty>
    </cac:EnvironmentalLegislationDocumentReference>
  </cac:TenderingTerms>
</cac:ProcurementProjectLot>
```

```json
{
  "parties": [
    {
      "id": "ORG-0001",
      "roles": [
        "informationProvider"
      ]
    }
  ],
  "tender": {
    "documents": [
      {
        "id": "Env1",
        "publisher": {
          "id": "ORG-0001"
        }
      }
    ]
  }
}
```

</td>
      </tr>
      <tr id="OPT-301-Part-FiscalLegis">
        <td class="field break-all">
            <p><b>OPT-301-Part-FiscalLegis</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/competition-results.html#tenderingPartySection"></a><br>Fiscal Legislation Organization Technical Identifier Reference</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='Part']/cac:TenderingTerms/cac:FiscalLegislationDocumentReference/cac:IssuerParty/cac:PartyIdentification/cbc:ID</span></code>
        </td>
        <td class="mapping">

<a href="operations.md#get-the-document-for-a-document-reference">Get the document for the document reference</a> and map to its `publisher.id`.

<a href="operations.md#get-the-organization-for-an-organization-technical-identifier-reference">Get the organization for the organization technical identifier reference</a> and add 'informationProvider' to is `roles` array.

```xml
<ext:UBLExtensions>
  <ext:UBLExtension>
    <ext:ExtensionContent>
      <efext:EformsExtension>
        <efac:Organizations>
          <efac:Organization>
            <efac:Company>
              <cac:PartyIdentification>
                <cbc:ID schemeName="organization">ORG-0001</cbc:ID>
              </cac:PartyIdentification>
            </efac:Company>
          </efac:Organization>
        </efac:Organizations>
      </efext:EformsExtension>
    </ext:ExtensionContent>
  </ext:UBLExtension>
</ext:UBLExtensions>
<cac:ProcurementProjectLot>
  <cac:TenderingTerms>
    <cac:FiscalLegislationDocumentReference>
      <cbc:ID>Fiscal1</cbc:ID>
      <cac:IssuerParty>
        <cac:PartyIdentification>
          <cbc:ID schemeName="organization">ORG-0001</cbc:ID>
        </cac:PartyIdentification>
      </cac:IssuerParty>
    </cac:FiscalLegislationDocumentReference>
  </cac:TenderingTerms>
</cac:ProcurementProjectLot>
```

```json
{
  "parties": [
    {
      "id": "ORG-0001",
      "roles": [
        "informationProvider"
      ]
    }
  ],
  "tender": {
    "documents": [
      {
        "id": "Fiscal1",
        "publisher": {
          "id": "ORG-0001"
        }
      }
    ]
  }
}
```

</td>
      </tr>
      <tr id="OPT-301-Part-Mediator">
        <td class="field break-all">
            <p><b>OPT-301-Part-Mediator</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/competition-results.html#tenderingPartySection"></a><br>Mediator Technical Identifier Reference</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='Part']/cac:TenderingTerms/cac:AppealTerms/cac:MediationParty/cac:PartyIdentification/cbc:ID</span></code>
        </td>
        <td class="mapping">

<a href="operations.md#get-the-organization-for-an-organization-technical-identifier-reference">Get the organization for the organization technical identifier reference</a> and add 'mediationBody, to the organization's `.roles` array.

```xml
<cac:MediationParty>
  <cac:PartyIdentification>
    <cbc:ID schemeName="organization">ORG-0003</cbc:ID>
  </cac:PartyIdentification>
</cac:MediationParty>
```

```json
{
  "parties": [
    {
      "id": "ORG-0003",
      "roles": [
        "mediationBody"
      ]
    }
  ]
}
```

</td>
      </tr>
      <tr id="OPT-301-Part-ReviewInfo">
        <td class="field break-all">
            <p><b>OPT-301-Part-ReviewInfo</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/procedure-lot-part-information.html#appealTermsSection"></a><br>Review Info Provider Technical Identifier Reference</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='Part']/cac:TenderingTerms/cac:AppealTerms/cac:AppealInformationParty/cac:PartyIdentification/cbc:ID</span></code>
        </td>
        <td class="mapping">

<a href="operations.md#get-the-organization-for-an-organization-technical-identifier-reference">Get the organization for the organization technical identifier reference</a> and add 'reviewContactPoint' to its `.roles` array.

```xml
<cac:ProcurementProjectLot>
  <cac:TenderingTerms>
    <cac:AppealTerms>
      <cac:AppealInformationParty>
        <cac:PartyIdentification>
          <cbc:ID schemeName="touchpoint">TPO-0001</cbc:ID>
        </cac:PartyIdentification>
      </cac:AppealInformationParty>
    </cac:AppealTerms>
  </cac:TenderingTerms>
</cac:ProcurementProjectLot>
```

```json
{
  "parties": [
    {
      "id": "TPO-0001",
      "roles": [
        "reviewContactPoint"
      ]
    }
  ]
}
```

</td>
      </tr>
      <tr id="OPT-301-Part-ReviewOrg">
        <td class="field break-all">
            <p><b>OPT-301-Part-ReviewOrg</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/competition-results.html#tenderingPartySection"></a><br>Review Organization Technical Identifier Reference</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='Part']/cac:TenderingTerms/cac:AppealTerms/cac:AppealReceiverParty/cac:PartyIdentification/cbc:ID</span></code>
        </td>
        <td class="mapping">

<a href="operations.md#get-the-organization-for-an-organization-technical-identifier-reference">Get the organization for the organization technical identifier reference</a> and add 'reviewBody, to the organization's `.roles` array.

```xml
<cac:AppealReceiverParty>
  <cac:PartyIdentification>
    <cbc:ID schemeName="touchpoint">TPO-0003</cbc:ID>
  </cac:PartyIdentification>
</cac:AppealReceiverParty>
```

```json
{
  "parties": [
    {
      "id": "TPO-0003",
      "roles": [
        "reviewBody"
      ]
    }
  ]
}
```

</td>
      </tr>
      <tr id="OPT-301-Part-TenderEval">
        <td class="field break-all">
            <p><b>OPT-301-Part-TenderEval</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/procedure-lot-part-information.html#partiesSection"></a><br>Tender Evaluator Technical Identifier Reference</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='Part']/cac:TenderingTerms/cac:TenderEvaluationParty/cac:PartyIdentification/cbc:ID</span></code>
        </td>
        <td class="mapping">

<a href="operations.md#get-the-organization-for-an-organization-technical-identifier-reference">Get the organization for the organization technical identifier reference</a> and add 'evaluationBody' to its `.roles` array.

```xml
<cac:ProcurementProjectLot>
  <cac:TenderingTerms>
    <cac:TenderEvaluationParty>
      <cac:PartyIdentification>
        <cbc:ID schemeName="touchpoint">TPO-0001</cbc:ID>
      </cac:PartyIdentification>
    </cac:TenderEvaluationParty>
  </cac:TenderingTerms>
</cac:ProcurementProjectLot>
```

```json
{
  "parties": [
    {
      "id": "TPO-0001",
      "roles": [
        "evaluationBody"
      ]
    }
  ]
}
```

</td>
      </tr>
      <tr id="OPT-301-Part-TenderReceipt">
        <td class="field break-all">
            <p><b>OPT-301-Part-TenderReceipt</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/procedure-lot-part-information.html#partiesSection"></a><br>Tender Recipient Technical Identifier Reference</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:ProcurementProjectLot[cbc:ID/@schemeName='Part']/cac:TenderingTerms/cac:TenderRecipientParty/cac:PartyIdentification/cbc:ID</span></code>
        </td>
        <td class="mapping">

<a href="operations.md#get-the-organization-for-an-organization-technical-identifier-reference">Get the organization for the organization technical identifier reference</a> and add 'submissionReceiptBody' to its `.roles` array.

```xml
<cac:ProcurementProjectLot>
  <cac:TenderingTerms>
    <cac:TenderRecipientParty>
      <cac:PartyIdentification>
        <cbc:ID schemeName="touchpoint">TPO-0001</cbc:ID>
      </cac:PartyIdentification>
    </cac:TenderRecipientParty>
  </cac:TenderingTerms>
</cac:ProcurementProjectLot>
```

```json
{
  "parties": [
    {
      "id": "TPO-0001",
      "roles": [
        "submissionReceiptBody"
      ]
    }
  ]
}
```

</td>
      </tr>
      <tr id="OPT-301-Tenderer-MainCont">
        <td class="field break-all">
            <p><b>OPT-301-Tenderer-MainCont</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/competition-results.html#tenderingPartySection"></a><br>Main Contractor ID Reference</p>
            <code class="docutils literal notranslate"><span class="pre">/*/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:NoticeResult/efac:TenderingParty/efac:SubContractor/efac:MainContractor/cbc:ID</span></code>
        </td>
        <td class="mapping">

- <a href="operations.md#get-the-organization-for-an-organization-technical-identifier-reference">Get the organization for the organization technical identifier reference</a> and add 'tenderer' to its `.roles` array.
- <a href="operations.md#get-the-bid-for-a-lottender">Get the bid for the LotTender</a>, and get the `subcontracts` object whose `subcontractors.id` is equal to the value of `ancestor: efac:SubContractor/cbc:ID`.
- Add an `OrganizationReference` object to the subcontract's `.tenderers` array and set its `.id` to the value of this field.

```xml
<efac:NoticeResult>
  <efac:LotTender>
    <cbc:ID schemeName="tender">TEN-0001</cbc:ID>
  </efac:LotTender>
  <efac:TenderingParty>
    <efac:SubContractor>
      <cbc:ID schemeName="organization">ORG-0012</cbc:ID>
      <efac:MainContractor>
        <cbc:ID schemeName="organization">ORG-0005</cbc:ID>
      </efac:MainContractor>
    </efac:SubContractor>
  </efac:TenderingParty>
</efac:NoticeResult>
<efac:Organizations>
  <efac:Organization>
    <efac:Company>
      <cac:PartyIdentification>
        <cbc:ID schemeName="organization">ORG-0005</cbc:ID>
      </cac:PartyIdentification>
    </efac:Company>
  </efac:Organization>
</efac:Organizations>
```

```json
{
  "parties": [
    {
      "id": "ORG-0005",
      "roles": [
        "tenderer"
      ]
    }
  ],
  "bids": {
    "details": [
      {
        "subcontracting": {
          "subcontracts": [
            {
              "id": "1",
              "subcontractor": {
                "id": "ORG-0012"
              },
              "tenderers": [
                {
                  "id": "ORG-0005",
                  "name": "Tendering Company Ltd"
                }
              ]
            }
          ]
        }
      }
    ]
  }
}
```

</td>
      </tr>
      <tr id="OPT-301-Tenderer-SubCont">
        <td class="field break-all">
            <p><b>OPT-301-Tenderer-SubCont</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/competition-results.html#tenderingPartySection"></a><br>Subcontractor ID Reference</p>
            <code class="docutils literal notranslate"><span class="pre">/*/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:NoticeResult/efac:TenderingParty/efac:SubContractor/cbc:ID</span></code>
        </td>
        <td class="mapping">

- <a href="operations.md#get-the-organization-for-an-organization-technical-identifier-reference">Get the organization for the organization technical identifier reference</a> and add 'subcontractor' to its `.roles` array.
- <a href="operations.md#get-the-bid-for-a-lottender">Get the bid for the LotTender</a>, add a `subcontracts` object to the bid's `.subcontracting.subcontracts` array, and:
  - Set its `.id` incrementally.
  - Add a `subcontractors` object and set its `.id` to the value of this field.

```xml
<efac:NoticeResult>
  <efac:LotTender>
    <cbc:ID schemeName="tender">TEN-0001</cbc:ID>
  </efac:LotTender>
  <efac:TenderingParty>
    <efac:SubContractor>
      <cbc:ID schemeName="organization">ORG-0012</cbc:ID>
    </efac:SubContractor>
  </efac:TenderingParty>
</efac:NoticeResult>
<efac:Organizations>
  <efac:Organization>
    <efac:Company>
      <cac:PartyIdentification>
        <cbc:ID schemeName="organization">ORG-0012</cbc:ID>
      </cac:PartyIdentification>
    </efac:Company>
  </efac:Organization>
</efac:Organizations>
```

```json
{
  "parties": [
    {
      "id": "ORG-0012",
      "roles": [
        "subcontractor"
      ]
    }
  ],
  "bids": {
    "details": [
      {
        "subcontracting": {
          "subcontracts": [
            {
              "id": "1",
              "subcontractor": {
                "id": "ORG-0012",
                "name": "Company ABC"
              }
            }
          ]
        }
      }
    ]
  }
}
```

</td>
      </tr>
      <tr id="OPT-302-Organization">
        <td class="field break-all">
            <p><b>OPT-302-Organization</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/parties.html#_general_structure_of_an_organization_related_information"></a><br>Beneficial Owner Reference</p>
            <code class="docutils literal notranslate"><span class="pre">/*/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:Organizations/efac:Organization/efac:UltimateBeneficialOwner/cbc:ID</span></code>
        </td>
        <td class="mapping">

Get the `Organization` in `parties` whose `id` is equal to the value of `ancestor::efac:Organization/efac:Company/cac:PartyIdentification/cbc:ID`. If none exists yet:

- Add an `Organization` to `parties`.
- Set its `.id` to the value of `ancestor::efac:Organization/efac:Company/cac:PartyIdentification/cbc:ID`.

If there is a `Person` in the organization's `.beneficialOwners` array whose `id` is equal to the value of this field, discard. Otherwise, add a `Person` to `.beneficialOwners` and map to its `.id`.

```xml
<efac:Organization>
  <efac:UltimateBeneficialOwner>
    <cbc:ID schemeName="ubo">UBO-0001</cbc:ID>
  </efac:UltimateBeneficialOwner>
</efac:Organization>
```

```json
{
  "parties": [
    {
      "beneficialOwners": [
        {
          "id": "UBO-0001"
        }
      ]
    }
  ]
}
```

</td>
      </tr>
      <tr id="OPT-310-Tender">
        <td class="field break-all">
            <p><b>OPT-310-Tender</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/competition-results.html#lotTenderSection"></a><br>Tendering Party ID Reference</p>
            <code class="docutils literal notranslate"><span class="pre">/*/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:NoticeResult/efac:LotTender/efac:TenderingParty/cbc:ID</span></code>
        </td>
        <td class="mapping">

- <a href="operations.md#get-the-bid-for-a-lottender">Get the bid for the LotTender</a> and get the `ancestor::efac:NoticeResult/efac:TenderingParty` whose `/cbc:ID` is equal to the value of this field.
- For each `/efac:Tenderer` in the tendering party:
  - <a href="operations.md#get-the-organization-for-a-tenderer">Get the organization for the tenderer</a>.
  - Add an `OrganizationReference` object to the bid's `.tenderers` array and set its `.id` to the organization's `.id`.

```xml
<efac:NoticeResult>
  <efac:LotTender>
    <efac:TenderingParty>
      <cbc:ID schemeName="tendering-party">TPA-0002</cbc:ID>
    </efac:TenderingParty>
  </efac:LotTender>
</efac:NoticeResult>
```

```json
{
  "bids": {
    "details": [
      {
        "tenderers": [
          {
            "id": "ORG-0011",
            "name": "Competitor"
          }
        ]
      }
    ]
  }
}
```

</td>
      </tr>
      <tr id="OPT-315-LotResult">
        <td class="field break-all">
            <p><b>OPT-315-LotResult</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/competition-results.html#_lot_result"></a><br>Contract Identifier Reference</p>
            <code class="docutils literal notranslate"><span class="pre">/*/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:NoticeResult/efac:LotResult/efac:SettledContract/cbc:ID</span></code>
        </td>
        <td class="mapping">

<a href="operations.md#get-the-contract-for-a-settledcontract">Get the contract for the SettledContract</a> and map to its `.id`.

```xml
<efac:LotResult>
  <efac:SettledContract>
    <cbc:ID schemeName="contract">CON-0001</cbc:ID>
  </efac:SettledContract>
</efac:LotResult>
```

```json
{
  "contracts": [
    {
      "id": "CON-0001",
      "awardID": "RES-0001"
    }
  ]
}
```

</td>
      </tr>
      <tr id="OPT-316-Contract">
        <td class="field break-all">
            <p><b>OPT-316-Contract</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/competition-results.html#settledContractSection"></a><br>Contract Technical Identifier</p>
            <code class="docutils literal notranslate"><span class="pre">/*/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:NoticeResult/efac:SettledContract/cbc:ID</span></code>
        </td>
        <td class="mapping">

If there is a `Contract` in `contracts` whose `.id` is equal to the value of this field discard. Otherwise:

- Add a `Contract` to `contracts`.
- Map to its `.id`.

```xml
<efac:NoticeResult>
  <efac:SettledContract>
    <cbc:ID schemeName="contract">CON-0001</cbc:ID>
  </efac:SettledContract>
</efac:NoticeResult>
```

```json
{
  "contracts": [
    {
      "id": "CON-0001"
    }
  ]
}
```

</td>
      </tr>
      <tr id="OPT-320-LotResult">
        <td class="field break-all">
            <p><b>OPT-320-LotResult</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/competition-results.html#_lot_result"></a><br>Tender Identifier Reference</p>
            <code class="docutils literal notranslate"><span class="pre">/*/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:NoticeResult/efac:LotResult/efac:LotTender/cbc:ID</span></code>
        </td>
        <td class="mapping">

<a href="operations.md#get-the-award-for-a-lotresult">Get the award for the LotResult</a> and add to its `.relatedBids` array.

```xml
<efac:NoticeResult>
  <efac:LotResult>
    <efac:LotTender>
      <cbc:ID schemeName="tender">TEN-0001</cbc:ID>
    </efac:LotTender>
    <efac:LotTender>
      <cbc:ID schemeName="tender">TEN-0002</cbc:ID>
    </efac:LotTender>
    <efac:LotTender>
      <cbc:ID schemeName="tender">TEN-0003</cbc:ID>
    </efac:LotTender>
  </efac:LotResult>
</efac:NoticeResult>
```

```json
{
  "awards": [
    {
      "relatedBids": [
        "TEN-0001",
        "TEN-0002",
        "TEN-0003"
      ]
    }
  ]
}
```

</td>
      </tr>
      <tr id="OPT-321-Tender">
        <td class="field break-all">
            <p><b>OPT-321-Tender</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/competition-results.html#lotTenderSection"></a><br>Tender Technical Identifier</p>
            <code class="docutils literal notranslate"><span class="pre">/*/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:NoticeResult/efac:LotTender/cbc:ID</span></code>
        </td>
        <td class="mapping">

If there is a `Bid` in `bids` whose `.id` is equal to the value of the field discard. Otherwise:

- Add a `Bid` to `bids`.
- Map to its `.id`.

```xml
<efac:LotTender>
  <cbc:ID schemeName="tender">TEN-0001</cbc:ID>
</efac:LotTender>
```

```json
{
  "bids": {
    "details": [
      {
        "id": "TEN-0001"
      }
    ]
  }
}
```

</td>
      </tr>
      <tr id="OPT-322-LotResult">
        <td class="field break-all">
            <p><b>OPT-322-LotResult</b> <a class="reference external" href="https://docs.ted.europa.eu/eforms/latest/schema/competition-results.html#_lot_result"></a><br>LotResult Technical Identifier</p>
            <code class="docutils literal notranslate"><span class="pre">/*/ext:UBLExtensions/ext:UBLExtension/ext:ExtensionContent/efext:EformsExtension/efac:NoticeResult/efac:LotResult/cbc:ID</span></code>
        </td>
        <td class="mapping">

If there is an `Award` in `awards` whose `.id` is equal to the value of this field discard. Otherwise:

- Add an `Award` to `awards`.
- Map to its `.id`.

```xml
<efac:LotResult>
  <cbc:ID schemeName="result">RES-0002</cbc:ID>
</efac:LotResult>
```

```json
{
  "awards": [
    {
      "id": "RES-0002"
    }
  ]
}
```

</td>
      </tr>
      <tr id="OPT-999">
        <td class="field break-all">
            <p><b>OPT-999</b> <br>Dummy Tender Award Date</p>
            <code class="docutils literal notranslate"><span class="pre">/*/cac:TenderResult/cbc:AwardDate</span></code>
        </td>
        <td class="mapping">







</td>
      </tr>
    </tbody>
  </table>
</div>

<script src="//cdnjs.cloudflare.com/ajax/libs/list.js/1.5.0/list.min.js"></script>
<script>new List('mappings', {valueNames: ['field', 'mapping']})</script>
