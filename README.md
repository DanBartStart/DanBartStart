<div class="span12" id="factfindContent" data-bind="template: { name: $root._view.newClientCurrentPage().id }, css: { span24: Client2(), span12: !Client2() }"><span class="debugInfo" style="display: none;">FF_ClientDetails</span><div class="row-fluid">
    <div class="wmpformheader form-horizontal" data-bind="css: { span12: $root.Client2, span24: !$root.Client2 }, with: $data.Client1">    
        <h2 data-bind="text: $data._computed.DisplayName() + '&nbsp;'">(New Client)&nbsp;</h2>
    </div>
    <div class="span12 wmpformheader form-horizontal" data-bind="with: $data.Client2, visible: $data.Client2()" style="display: none;"></div>
</div>
<div class="row-fluid">
    <div class="wmpformpanel form-horizontal" data-bind="css: { span12: $root.Client2, span24: !$root.Client2 }, with: $data.Client1">
        <div class="centeredDiv">
            <div class="padded control-group" data-bind="visible: $root.Client2()" style="display: none;">
                <label class="control-label">Relationship to client 2</label>
                <div class="controls">
                    <select class="input-medium" data-bind="AMLDisable: 1, options: $data._computed.CODE_ASSOCIATION_TYPE, optionsCaption: '', optionsText: 'DESCRIPTION', optionsValue: 'ID', value: $data._computed.CODE_ASSOCIATION_TYPE_ID" title="" data-testid="8D08183C-0AFE-4BBF-BA33-6C0C062DEA58"><option value=""></option><option value="7">Husband</option><option value="8">Wife</option><option value="9">Partner</option><option value="28">Civil Partner</option><option value="1">Son</option><option value="2">Daughter</option><option value="21">Mother</option><option value="22">Father</option><option value="36">Brother</option><option value="37">Sister</option><option value="10">Stepson</option><option value="11">Step Daughter</option><option value="38">Grandmother</option><option value="39">Grandfather</option><option value="30">Niece</option><option value="12">Nephew</option><option value="13">Cousin</option><option value="14">Second Cousin</option><option value="15">Aunt</option><option value="16">Uncle</option><option value="17">Grandson</option><option value="18">Granddaughter</option><option value="19">Great Grandson</option><option value="20">Great Granddaughter</option><option value="40">Great Grandmother</option><option value="41">Great Grandfather</option><option value="25">Father in Law</option><option value="26">Mother in Law</option><option value="27">Friend</option><option value="23">Step Mother</option><option value="24">Step Father</option><option value="31">Accountant</option><option value="32">Solicitor</option><option value="33">Trustee</option><option value="35">POA (Prop &amp; Fin Affairs)</option><option value="29">No Relationship</option>
                    </select>
                    <!--$data._computed.AvailableRelationshipTypes1-->
                </div>
            </div>
        </div>

        <h3>
            Name</h3>
            <div class="centeredDiv">
                 <div class="control-group error" data-bind="validationElement: $data._view.titleValidationElement" title="">
                    <label class="control-label">
                        Title<sup>*</sup></label>
                    <div class="controls">
                        <div class="input-append">
                            <input type="text" class="input-medium" data-bind="AMLDisable: 1, value: $data.OTHER_TITLE, visible: $data.CODE_TITLE_ID() == 8" placeholder="Other (Please Specify)" title="" data-testid="CB7028FA-42E5-4475-86A7-F0789CF1456D" style="display: none;">
                            <span data-bind="visible: $data.CODE_TITLE_ID() == 8, click: $data._methods.ClearCustomTitle" class="add-on hover-pointer" style="display: none;">
                                <i class="icon-cross" title="Reset title"></i>
                            </span>
                        </div>
                        <select class="select-medium error" data-bind="AMLDisable: 1, visible: $data.CODE_TITLE_ID() != 8, options: BDFactfind._codes.GetCodeTable('CODE_TITLE'), optionsText: 'DESCRIPTION', optionsValue: 'ID', value: $data.CODE_TITLE_ID" title="Title is required" data-orig-title="" data-testid="89495CE1-1634-49E8-AD56-9517D5A34943"><option value="0"></option><option value="1">Mr</option><option value="2">Mrs</option><option value="10">Master</option><option value="3">Miss</option><option value="4">Ms</option><option value="5">Dr</option><option value="7">Professor</option><option value="6">Reverend</option><option value="13">Sir</option><option value="15">Dame</option><option value="12">The Lord</option><option value="14">The Lady</option><option value="16">The Honourable</option><option value="8">Other (Please Specify)</option>
                        </select>
                        <!--options: $data._view.AvailableTitles-->
                    </div>
                </div>
                <!--<div class="control-group" data-bind="visible: $data.CODE_TITLE_ID() === 8, validationElement: $data.OTHER_TITLE">
                    <label class="control-label">
                        Other title</label>
                    <div class="controls">
                        <input type="text" data-bind="value: $data.OTHER_TITLE" /></div>
                </div>-->
                <div class="control-group error" data-bind="validationElement: $data.FORENAME" title="Forename is required" data-orig-title="">
                    <label class="control-label" style="text-transform: none !important">
                        Forename(s)<sup>*</sup></label>
                    <div class="controls">
                        <input type="text" data-bind="AMLDisable: 1, value: $data.FORENAME" class="error" title="Forename is required" data-orig-title="" data-testid="082F53AE-2B38-4E9F-B501-E3AD0E597C6C"></div>
                </div>
                <div class="control-group error" data-bind="validationElement: $data.SURNAME" title="Surname is required" data-orig-title="">
                    <label class="control-label">
                        Surname<sup>*</sup></label>
                    <div class="controls">
                        <!-- Syncing married surnames is now handled in BD_CLNT_CLIENT_DETAIL.js using KO postbox library -->
                        <input type="text" data-bind="AMLDisable: 1, value: $data.SURNAME" class="error" title="Surname is required" data-orig-title="" data-testid="2FBE8694-ADA5-4A37-BBF1-BB9A79C54C8C">
                    </div>
                </div>
                <div class="control-group">
                    <label class="control-label">
                    </label>
                    <div class="controls checkbox">
                        <input type="checkbox" data-bind="checked: $data.BD_CLNT_CLIENT_PREVIOUS_SURNAMES().length > 0, click: $data._methods.BD_CLNT_CLIENT_PREVIOUS_SURNAMES_Click" data-testid="8E2C3A33-402F-4FF0-99B8-897A6999BEB2">Previous
                        Surname(s)?
                    </div>
                </div>
                <div data-bind="foreach: $data.BD_CLNT_CLIENT_PREVIOUS_SURNAMES"></div>                
                <div class="control-group">
                    <label class="control-label">
                    </label>
                    <div class="controls checkbox">
                        <input type="checkbox" data-bind="checked: $data.BD_CLNT_CLIENT_HONOURS().length > 0, click: $data._methods.BD_CLNT_CLIENT_HONOURS_Click" data-testid="1133984E-4EFA-4FAF-85FE-8529C8ABDE98">Honours,
                        decorations &amp; medals?
                    </div>
                </div>
                <div data-bind="foreach: $data.BD_CLNT_CLIENT_HONOURS"></div>
                <div class="control-group">
                    <label class="control-label">
                        Known as</label>
                    <div class="controls">
                        <input type="text" data-bind="AMLDisable: 1, value: $data.KNOWN_AS" title="" data-testid="71E3B300-C976-49AF-B13C-D7E360D7CA67">
                    </div>
                </div>
                <div class="control-group">
                    <label class="control-label">
                        Correspondence salutation</label>
                    <div class="controls">
                        <select class="input-medium" data-bind="AMLDisable: 1, options: BDFactfind._codes.GetCodeTable('CODE_CORRESPONDENCESALUTATION'), optionsText: 'DESCRIPTION', optionsValue: 'ID', value: $data.CODE_CORRESPONDENCESALUTATION_ID" title="" data-testid="F0B4FF20-6747-4A6C-B14D-60C90FD92FD4"><option value="0"></option><option value="1">Forename</option><option value="2">Title &amp; Surname</option><option value="3">Known As</option>
                        </select>
                    </div>
                </div>
            </div>
    </div>

    <!--<div class="span12 wmpformpanel form-horizontal" data-bind="visible: ($root.Client2() && $root.Client2()._view.viewMode() === 'relationship'), with: $data.Client2">
        <div class="padded control-group">
            <label class="control-label">Relation to client 1</label>
            <div class="controls">
                <select class="input-medium" data-bind="options: $data._computed.AvailableRelationshipTypes, optionsText: 'DESCRIPTION', optionsValue: 'ID', value: $root.Client2AssociationId">
                </select>
            </div>
        </div>

        <div class="row-fluid span24">
            <span class="span12">
                <button class="btn btn-small btn-block btn-primary" data-bind="click: $root._methods.AddClient2"><i class="icon-plus-sign"></i>&nbsp;Add Client 2</button>
            </span>
            <span class="span12">
                <button class="btn btn-small btn-block" data-bind="click: $root._methods.RemoveClient2"><i class="icon-cross"></i>&nbsp;Cancel</button>
            </span>
        </div>

    </div> -->

    <div class="span12 wmpformpanel form-horizontal" data-bind="with: $data.Client2, visible: $data.Client2()" style="display: none;"></div>
</div>
<div class="row-fluid">
    <div class="wmpformpanel form-horizontal" data-bind="css: { span12: $root.Client2, span24: !$root.Client2 }, with: $data.Client1">
        <h3>
            Personal details</h3>
        <div class="row-fluid">
            <div class="centeredDiv">
                <div class="span24">
                        <div class="control-group" data-bind="validationElement: $data.CODE_GENDER_ID" title="">
                            <label class="control-label">
                                Gender</label>
                            <div class="controls">
                                <span>
                                    <input type="radio" data-bind="AMLDisable: 1, attr: { 'name': $data.CLNT_CLIENT_ID() + '_CODE_GENDER_ID' }, checked: $data._computed.CODE_GENDER_ID" value="1" name="0A5C601A-4EC5-465F-9358-EEA1F72EC1C3_CODE_GENDER_ID" data-testid="79D24F4F-7BED-4450-9B7F-0DCA1D13286A" title="">Male</span>&nbsp;&nbsp;<span>
                                            <input type="radio" data-bind="AMLDisable: 1, attr: { 'name': $data.CLNT_CLIENT_ID() + '_CODE_GENDER_ID' }, checked: $data._computed.CODE_GENDER_ID" value="2" name="0A5C601A-4EC5-465F-9358-EEA1F72EC1C3_CODE_GENDER_ID" data-testid="9C878C6F-6141-4B5C-858D-EAC8000B29F7" title="">Female</span>
                            </div>
                        </div>
                        <div class="control-group error" data-bind="validationElement: $data.DOB" title="Date of Birth is required and must be a valid date and must be after '15/08/1873' and must be before '15/08/2023'" data-orig-title="">
                            <label class="control-label">
                                Date of birth<sup>*</sup></label>
                            <div class="controls">
                                <div class="input-append">
<!--
                                    <input type="text" data-date-format="dd/mm/yyyy" placeholder="dd/mm/yyyy" class="input-small datePicker" data-bind="datepicker: $data.DOB, datepickerOptions: { minDate: new Date(), format: 'dd/mm/yyyy', autoclose: true }">
                                    <span onclick="javascript:$(this).datepicker();" class="add-on">
                                        <i class="icon-calendar"></i>
                                    </span>
-->
                                    <input type="text" placeholder="dd/mm/yyyy" class="input-medium" data-bind="AMLDisable: 1, dateString: $data.DOB">
                                    <span class="add-on">
                                        <i class="icon-calendar"></i>
                                    </span>
                                    &nbsp;&nbsp;Age:
                                    <span data-bind="text: $data._computed.Age()"></span>
                                </div>
                            </div>
                        </div>
                        <div class="control-group">
                            <label class="control-label">
                                Marital status
                            </label>
                            <div class="controls">
                                <select data-bind="options: BDFactfind._codes.GetCodeTable('CODE_MARITAL'), optionsText: 'DESCRIPTION', optionsValue: 'ID', value: $data.CODE_MARITAL_ID" title="" data-testid="99C03941-4460-4E3E-BD89-DDF7524711A2"><option value="0"></option><option value="4">Single</option><option value="1">Married</option><option value="9">Civil Partnership</option><option value="5">Living with Partner</option><option value="2">Divorced</option><option value="6">Separated</option><option value="3">Widowed</option>
                                </select>
                            </div>
                        </div>
                </div>
            </div>
        </div>
    </div>
    <div class="span12 wmpformpanel form-horizontal" data-bind="with: $data.Client2, visible: $data.Client2()" style="display: none;"></div>
</div>
<div class="row-fluid">
    <div class="wmpformpanel form-horizontal" data-bind="css: { span12: $root.Client2, span24: !$root.Client2 }, with: $data.Client1">
        <h3>
            Country of birth, nationality &amp; Domicile</h3>
        <div class="row-fluid">
            <div class="span24">
                <div class="centeredDiv">
                    <div class="control-group" data-bind="validationElement: $data.CODE_BIRTH_COUNTRY_ID" title="">
                        <label class="control-label">
                            Country of Birth<sup>*</sup></label>
                        <div class="controls">
                            <select data-bind="AMLDisable: 1, options: BDFactfind._codes.GetCodeTable('CODE_COUNTRY'), optionsText: 'DESCRIPTION', optionsValue: 'ID', value: $data.CODE_BIRTH_COUNTRY_ID" title="" data-testid="8DCFA19D-7EEB-4A4C-A5A7-F416FE390208"><option value="4">Afghanistan</option><option value="248">Åland Islands</option><option value="8">Albania</option><option value="12">Algeria</option><option value="16">American Samoa</option><option value="20">Andorra</option><option value="24">Angola</option><option value="660">Anguilla</option><option value="10">Antarctica</option><option value="28">Antigua and Barbuda</option><option value="32">Argentina</option><option value="51">Armenia</option><option value="533">Aruba</option><option value="36">Australia</option><option value="40">Austria</option><option value="31">Azerbaijan</option><option value="44">Bahamas</option><option value="48">Bahrain</option><option value="50">Bangladesh</option><option value="52">Barbados</option><option value="112">Belarus</option><option value="56">Belgium</option><option value="84">Belize</option><option value="204">Benin</option><option value="60">Bermuda</option><option value="64">Bhutan</option><option value="68">Bolivia, Plurinational State of</option><option value="535">Bonaire, Sint Eustatius and Saba</option><option value="70">Bosnia and Herzegovina</option><option value="72">Botswana</option><option value="74">Bouvet Island</option><option value="76">Brazil</option><option value="86">British Indian Ocean Territory</option><option value="96">Brunei Darussalam</option><option value="100">Bulgaria</option><option value="854">Burkina Faso</option><option value="108">Burundi</option><option value="132">Cabo Verde</option><option value="116">Cambodia</option><option value="120">Cameroon</option><option value="124">Canada</option><option value="136">Cayman Islands</option><option value="140">Central African Republic</option><option value="148">Chad</option><option value="152">Chile</option><option value="156">China</option><option value="162">Christmas Island</option><option value="166">Cocos (Keeling) Islands</option><option value="170">Colombia</option><option value="174">Comoros</option><option value="178">Congo</option><option value="180">Congo, the Democratic Republic of the</option><option value="184">Cook Islands</option><option value="188">Costa Rica</option><option value="384">Côte d'Ivoire</option><option value="191">Croatia</option><option value="192">Cuba</option><option value="531">Curaçao</option><option value="196">Cyprus</option><option value="203">Czech Republic</option><option value="208">Denmark</option><option value="262">Djibouti</option><option value="212">Dominica</option><option value="214">Dominican Republic</option><option value="218">Ecuador</option><option value="818">Egypt</option><option value="222">El Salvador</option><option value="226">Equatorial Guinea</option><option value="232">Eritrea</option><option value="233">Estonia</option><option value="231">Ethiopia</option><option value="238">Falkland Islands (Malvinas)</option><option value="234">Faroe Islands</option><option value="242">Fiji</option><option value="246">Finland</option><option value="250">France</option><option value="254">French Guiana</option><option value="258">French Polynesia</option><option value="260">French Southern Territories</option><option value="266">Gabon</option><option value="270">Gambia</option><option value="268">Georgia</option><option value="276">Germany</option><option value="288">Ghana</option><option value="292">Gibraltar</option><option value="300">Greece</option><option value="304">Greenland</option><option value="308">Grenada</option><option value="312">Guadeloupe</option><option value="316">Guam</option><option value="320">Guatemala</option><option value="831">Guernsey</option><option value="324">Guinea</option><option value="624">Guinea-Bissau</option><option value="328">Guyana</option><option value="332">Haiti</option><option value="334">Heard Island and McDonald Islands</option><option value="336">Holy See (Vatican City State)</option><option value="340">Honduras</option><option value="344">Hong Kong</option><option value="348">Hungary</option><option value="352">Iceland</option><option value="356">India</option><option value="360">Indonesia</option><option value="364">Iran, Islamic Republic of</option><option value="368">Iraq</option><option value="372">Ireland</option><option value="833">Isle of Man</option><option value="376">Israel</option><option value="380">Italy</option><option value="388">Jamaica</option><option value="392">Japan</option><option value="832">Jersey</option><option value="400">Jordan</option><option value="398">Kazakhstan</option><option value="404">Kenya</option><option value="296">Kiribati</option><option value="408">Korea, Democratic People's Republic of</option><option value="410">Korea, Republic of</option><option value="414">Kuwait</option><option value="417">Kyrgyzstan</option><option value="418">Lao People's Democratic Republic</option><option value="428">Latvia</option><option value="422">Lebanon</option><option value="426">Lesotho</option><option value="430">Liberia</option><option value="434">Libya</option><option value="438">Liechtenstein</option><option value="440">Lithuania</option><option value="442">Luxembourg</option><option value="446">Macao</option><option value="807">Macedonia, the former Yugoslav Republic of</option><option value="450">Madagascar</option><option value="454">Malawi</option><option value="458">Malaysia</option><option value="462">Maldives</option><option value="466">Mali</option><option value="470">Malta</option><option value="584">Marshall Islands</option><option value="474">Martinique</option><option value="478">Mauritania</option><option value="480">Mauritius</option><option value="175">Mayotte</option><option value="484">Mexico</option><option value="583">Micronesia, Federated States of</option><option value="498">Moldova, Republic of</option><option value="492">Monaco</option><option value="496">Mongolia</option><option value="499">Montenegro</option><option value="500">Montserrat</option><option value="504">Morocco</option><option value="508">Mozambique</option><option value="104">Myanmar</option><option value="516">Namibia</option><option value="520">Nauru</option><option value="524">Nepal</option><option value="528">Netherlands</option><option value="540">New Caledonia</option><option value="554">New Zealand</option><option value="558">Nicaragua</option><option value="562">Niger</option><option value="566">Nigeria</option><option value="570">Niue</option><option value="574">Norfolk Island</option><option value="580">Northern Mariana Islands</option><option value="578">Norway</option><option value="512">Oman</option><option value="586">Pakistan</option><option value="585">Palau</option><option value="275">Palestine, State of</option><option value="591">Panama</option><option value="598">Papua New Guinea</option><option value="600">Paraguay</option><option value="604">Peru</option><option value="608">Philippines</option><option value="612">Pitcairn</option><option value="616">Poland</option><option value="620">Portugal</option><option value="630">Puerto Rico</option><option value="634">Qatar</option><option value="638">Réunion</option><option value="642">Romania</option><option value="643">Russian Federation</option><option value="646">Rwanda</option><option value="652">Saint Barthélemy</option><option value="654">Saint Helena, Ascension and Tristan da Cunha</option><option value="659">Saint Kitts and Nevis</option><option value="662">Saint Lucia</option><option value="663">Saint Martin (French part)</option><option value="666">Saint Pierre and Miquelon</option><option value="670">Saint Vincent and the Grenadines</option><option value="882">Samoa</option><option value="674">San Marino</option><option value="678">Sao Tome and Principe</option><option value="682">Saudi Arabia</option><option value="686">Senegal</option><option value="688">Serbia</option><option value="690">Seychelles</option><option value="694">Sierra Leone</option><option value="702">Singapore</option><option value="534">Sint Maarten (Dutch part)</option><option value="703">Slovakia</option><option value="705">Slovenia</option><option value="90">Solomon Islands</option><option value="706">Somalia</option><option value="710">South Africa</option><option value="239">South Georgia and the South Sandwich Islands</option><option value="728">South Sudan</option><option value="724">Spain</option><option value="144">Sri Lanka</option><option value="729">Sudan</option><option value="740">Suriname</option><option value="744">Svalbard and Jan Mayen</option><option value="748">Swaziland</option><option value="752">Sweden</option><option value="756">Switzerland</option><option value="760">Syrian Arab Republic</option><option value="158">Taiwan, Province of China</option><option value="762">Tajikistan</option><option value="834">Tanzania, United Republic of</option><option value="764">Thailand</option><option value="626">Timor-Leste</option><option value="768">Togo</option><option value="772">Tokelau</option><option value="776">Tonga</option><option value="780">Trinidad and Tobago</option><option value="788">Tunisia</option><option value="792">Turkey</option><option value="795">Turkmenistan</option><option value="796">Turks and Caicos Islands</option><option value="798">Tuvalu</option><option value="800">Uganda</option><option value="804">Ukraine</option><option value="784">United Arab Emirates</option><option value="826">United Kingdom</option><option value="840">United States</option><option value="581">United States Minor Outlying Islands</option><option value="858">Uruguay</option><option value="860">Uzbekistan</option><option value="548">Vanuatu</option><option value="862">Venezuela, Bolivarian Republic of</option><option value="704">Viet Nam</option><option value="92">Virgin Islands, British</option><option value="850">Virgin Islands, U.S.</option><option value="876">Wallis and Futuna</option><option value="732">Western Sahara</option><option value="887">Yemen</option><option value="894">Zambia</option><option value="716">Zimbabwe</option>
                            </select>
                        </div>
                    </div>
                    <div class="control-group" data-bind="validationElement: $data.CODE_NATIONALITY_COUNTRY_ID" title="">
                        <label class="control-label">
                            Nationality<sup>*</sup></label>
                        <div class="controls">
                            <select data-bind="AMLDisable: 1, options: BDFactfind._codes.GetCodeTable('CODE_NATIONALITY'), optionsText: 'DESCRIPTION', optionsValue: 'ID', value: $data.CODE_NATIONALITY_COUNTRY_ID" title="" data-testid="063B12F0-16B0-4D51-96E1-1FE986FD2CF2"><option value="0"></option><option value="4">Afghan</option><option value="248">Åland Islands</option><option value="8">Albanian </option><option value="12">Algerian</option><option value="16">American Samoa</option><option value="20">Andorran</option><option value="24">Angolan</option><option value="660">Anguilla</option><option value="10">Antarctica</option><option value="32">Argentine; Argentinian</option><option value="51">Armenian</option><option value="533">Aruba</option><option value="36">Australian </option><option value="40">Austrian</option><option value="31">Azerbaijani</option><option value="44">Bahamian</option><option value="48">Bahraini</option><option value="50">Bangladeshi</option><option value="52">Barbadian</option><option value="112">Belarusian</option><option value="56">Belgian</option><option value="204">Beninese</option><option value="60">Bermuda</option><option value="64">Bhutanese</option><option value="68">Bolivian</option><option value="535">Bonaire, Sint Eustatius and Saba</option><option value="74">Bouvet Island</option><option value="76">Brazilian</option><option value="826">British</option><option value="86">British Indian Ocean Territory</option><option value="100">Bulgarian</option><option value="854">Burkinabe, Burkinan</option><option value="104">Burmese</option><option value="116">Cambodian</option><option value="120">Cameroonian</option><option value="124">Canadian</option><option value="132">Cape Verdean</option><option value="136">Cayman Islands</option><option value="148">Chadian</option><option value="152">Chilean</option><option value="156">Chinese</option><option value="162">Christmas Island</option><option value="28">Citizen of Antigua and Barbuda</option><option value="84">Citizen of Belize</option><option value="70">Citizen of Bosnia and Herzegovina</option><option value="72">Citizen of Botswana</option><option value="96">Citizen of Brunei</option><option value="108">Citizen of Burundi</option><option value="242">Citizen of Fiji</option><option value="624">Citizen of Guinea-Bissau</option><option value="372">Citizen of Ireland, Irish citizen</option><option value="296">Citizen of Kiribati</option><option value="426">Citizen of Lesotho</option><option value="450">Citizen of Madagascar</option><option value="458">Citizen of Malaysia</option><option value="562">Citizen of Niger</option><option value="674">Citizen of San Marino</option><option value="678">Citizen of Sao Tome and Principe</option><option value="690">Citizen of Seychelles</option><option value="144">Citizen of Sri Lanka</option><option value="659">Citizen of St Christopher (St Kitts) and Nevis</option><option value="140">Citizen of the Central African Republic</option><option value="408">Citizen of the Democratic People's Republic of Korea; Citizen of the DPRK</option><option value="180">Citizen of The Democratic Republic of the Congo</option><option value="214">Citizen of the Dominican Republic</option><option value="384">Citizen of the Ivory Coast</option><option value="178">Citizen of the Republic of the Congo</option><option value="784">Citizen of the United Arab Emirates</option><option value="548">Citizen of Vanuatu</option><option value="166">Cocos (Keeling) Islands</option><option value="170">Colombian</option><option value="174">Comoran</option><option value="184">Cook Islands</option><option value="188">Costa Rican</option><option value="191">Croatian</option><option value="192">Cuban</option><option value="531">Curaçao</option><option value="196">Cypriot</option><option value="203">Czech</option><option value="208">Dane</option><option value="262">Djiboutian</option><option value="212">Dominican</option><option value="528">Dutch citizen; Dutchman; Dutchwoman</option><option value="626">East Timorese</option><option value="218">Ecuadorean</option><option value="818">Egyptian </option><option value="226">Equatorial Guinean</option><option value="232">Eritrean</option><option value="233">Estonian</option><option value="231">Ethiopian</option><option value="238">Falkland Islands (Malvinas)</option><option value="234">Faroe Islands</option><option value="608">Filipino (male), Filipina (female)</option><option value="246">Finn</option><option value="250">French citizen; Frenchman; Frenchwoman</option><option value="254">French Guiana</option><option value="258">French Polynesia</option><option value="260">French Southern Territories</option><option value="266">Gabonese</option><option value="270">Gambian</option><option value="268">Georgian</option><option value="276">German</option><option value="288">Ghanaian</option><option value="292">Gibraltar</option><option value="300">Greek</option><option value="304">Greenland</option><option value="308">Grenadian</option><option value="312">Guadeloupe</option><option value="316">Guam</option><option value="320">Guatemalan</option><option value="831">Guernsey</option><option value="324">Guinean</option><option value="328">Guyanese</option><option value="332">Haitian</option><option value="334">Heard Island and McDonald Islands</option><option value="340">Honduran</option><option value="344">Hong Kong</option><option value="348">Hungarian</option><option value="352">Icelander</option><option value="356">Indian</option><option value="360">Indonesian</option><option value="364">Iranian</option><option value="368">Iraqi</option><option value="833">Isle of Man</option><option value="376">Israeli</option><option value="380">Italian</option><option value="388">Jamaican</option><option value="392">Japanese</option><option value="832">Jersey</option><option value="400">Jordanian</option><option value="398">Kazakh</option><option value="404">Kenyan</option><option value="414">Kuwaiti</option><option value="417">Kyrgyz</option><option value="418">Lao</option><option value="428">Latvian</option><option value="422">Lebanese</option><option value="430">Liberian</option><option value="434">Libyan</option><option value="438">Liechtenstein citizen</option><option value="440">Lithuanian</option><option value="442">Luxembourger</option><option value="446">Macao</option><option value="807">Macedonian</option><option value="454">Malawian</option><option value="462">Maldivian</option><option value="466">Malian</option><option value="470">Maltese</option><option value="584">Marshall Islander</option><option value="474">Martinique</option><option value="478">Mauritanian</option><option value="480">Mauritian</option><option value="175">Mayotte</option><option value="484">Mexican</option><option value="583">Micronesian</option><option value="498">Moldovan</option><option value="492">Monegasque</option><option value="496">Mongolian</option><option value="499">Montenegrin</option><option value="500">Montserrat</option><option value="504">Moroccan</option><option value="508">Mozambican</option><option value="516">Namibian</option><option value="520">Nauruan</option><option value="524">Nepalese</option><option value="540">New Caledonia</option><option value="554">New Zealander</option><option value="558">Nicaraguan</option><option value="566">Nigerian</option><option value="570">Niue</option><option value="574">Norfolk Island</option><option value="580">Northern Mariana Islands</option><option value="578">Norwegian</option><option value="512">Omani</option><option value="586">Pakistani</option><option value="585">Palauan</option><option value="275">Palestine, State of</option><option value="591">Panamanian</option><option value="598">Papua New Guinean</option><option value="600">Paraguayan</option><option value="604">Peruvian</option><option value="612">Pitcairn</option><option value="616">Pole</option><option value="620">Portuguese</option><option value="630">Puerto Rico</option><option value="634">Qatari</option><option value="638">Réunion</option><option value="642">Romanian</option><option value="643">Russian</option><option value="646">Rwandan</option><option value="652">Saint Barthélemy</option><option value="654">Saint Helena, Ascension and Tristan da Cunha</option><option value="663">Saint Martin (French part)</option><option value="666">Saint Pierre and Miquelon</option><option value="222">Salvadorean</option><option value="882">Samoan</option><option value="682">Saudi Arabian</option><option value="686">Senegalese</option><option value="688">Serbian</option><option value="694">Sierra Leonean</option><option value="702">Singaporean</option><option value="534">Sint Maarten (Dutch part)</option><option value="703">Slovak</option><option value="705">Slovene</option><option value="90">Solomon Islander</option><option value="706">Somali</option><option value="710">South African</option><option value="239">South Georgia and the South Sandwich Islands</option><option value="410">South Korean</option><option value="728">South Sudanese</option><option value="724">Spaniard, Spanish citizen</option><option value="662">St Lucian</option><option value="729">Sudanese</option><option value="740">Surinamer</option><option value="744">Svalbard and Jan Mayen</option><option value="748">Swazi</option><option value="752">Swede</option><option value="756">Swiss</option><option value="760">Syrian</option><option value="158">Taiwan, Province of China</option><option value="762">Tajik</option><option value="834">Tanzanian</option><option value="764">Thai</option><option value="768">Togolese</option><option value="772">Tokelau</option><option value="776">Tongan</option><option value="780">Trinidad and Tobago citizen</option><option value="788">Tunisian</option><option value="792">Turk</option><option value="795">Turkmen</option><option value="796">Turks and Caicos Islands</option><option value="798">Tuvaluan</option><option value="800">Ugandan</option><option value="804">Ukrainian</option><option value="840">United States citizen</option><option value="581">United States Minor Outlying Islands</option><option value="858">Uruguayan</option><option value="860">Uzbek</option><option value="336">Vatican citizen</option><option value="862">Venezuelan</option><option value="704">Vietnamese</option><option value="670">Vincentian</option><option value="92">Virgin Islands, British</option><option value="850">Virgin Islands, U.S.</option><option value="876">Wallis and Futuna</option><option value="732">Western Sahara</option><option value="887">Yemeni</option><option value="894">Zambian</option><option value="716">Zimbabwean</option>
                            </select>
                        </div>
                    </div>
                    <div class="control-group" data-bind="validationElement: $data.DUAL_NATIONALITY" title="">
                        <label class="control-label">
                            Dual Nationality?</label>
                        <div class="controls">
                            <span>
                                <input type="radio" data-bind="AMLDisable: 1, attr: { 'name': $data.CLNT_CLIENT_ID() + '_DUAL_NATIONALITY' }, checked: $data._computed.DUAL_NATIONALITY" value="1" name="0A5C601A-4EC5-465F-9358-EEA1F72EC1C3_DUAL_NATIONALITY" data-testid="BBEF76AE-3322-4DDE-8871-348667E53431" title="">Yes</span> <span>
                                        <input type="radio" data-bind="AMLDisable: 1, attr: { 'name': $data.CLNT_CLIENT_ID() + '_DUAL_NATIONALITY' }, checked: $data._computed.DUAL_NATIONALITY" value="0" name="0A5C601A-4EC5-465F-9358-EEA1F72EC1C3_DUAL_NATIONALITY" data-testid="CA847466-3D42-49E1-B21C-3BF001A2BD22" title="">No</span>
                        </div>
                    </div>
                    <div class="control-group" data-bind="visible: $data._computed.DUAL_NATIONALITY() == '1', validationElement: $data.CODE_OTHER_NATIONALITY_COUNTRY_ID" title="" style="display: none;">
                        <label class="control-label">
                            Other Nationality<sup>*</sup></label>
                        <div class="controls">
                            <select data-bind="AMLDisable: 1, options: BDFactfind._codes.GetCodeTable('CODE_NATIONALITY'), optionsText: 'DESCRIPTION', optionsValue: 'ID', value: $data.CODE_OTHER_NATIONALITY_COUNTRY_ID" title="" data-testid="4D1E8F2F-FCD1-4C4C-A7A0-0B50D28D18C7"><option value="0"></option><option value="4">Afghan</option><option value="248">Åland Islands</option><option value="8">Albanian </option><option value="12">Algerian</option><option value="16">American Samoa</option><option value="20">Andorran</option><option value="24">Angolan</option><option value="660">Anguilla</option><option value="10">Antarctica</option><option value="32">Argentine; Argentinian</option><option value="51">Armenian</option><option value="533">Aruba</option><option value="36">Australian </option><option value="40">Austrian</option><option value="31">Azerbaijani</option><option value="44">Bahamian</option><option value="48">Bahraini</option><option value="50">Bangladeshi</option><option value="52">Barbadian</option><option value="112">Belarusian</option><option value="56">Belgian</option><option value="204">Beninese</option><option value="60">Bermuda</option><option value="64">Bhutanese</option><option value="68">Bolivian</option><option value="535">Bonaire, Sint Eustatius and Saba</option><option value="74">Bouvet Island</option><option value="76">Brazilian</option><option value="826">British</option><option value="86">British Indian Ocean Territory</option><option value="100">Bulgarian</option><option value="854">Burkinabe, Burkinan</option><option value="104">Burmese</option><option value="116">Cambodian</option><option value="120">Cameroonian</option><option value="124">Canadian</option><option value="132">Cape Verdean</option><option value="136">Cayman Islands</option><option value="148">Chadian</option><option value="152">Chilean</option><option value="156">Chinese</option><option value="162">Christmas Island</option><option value="28">Citizen of Antigua and Barbuda</option><option value="84">Citizen of Belize</option><option value="70">Citizen of Bosnia and Herzegovina</option><option value="72">Citizen of Botswana</option><option value="96">Citizen of Brunei</option><option value="108">Citizen of Burundi</option><option value="242">Citizen of Fiji</option><option value="624">Citizen of Guinea-Bissau</option><option value="372">Citizen of Ireland, Irish citizen</option><option value="296">Citizen of Kiribati</option><option value="426">Citizen of Lesotho</option><option value="450">Citizen of Madagascar</option><option value="458">Citizen of Malaysia</option><option value="562">Citizen of Niger</option><option value="674">Citizen of San Marino</option><option value="678">Citizen of Sao Tome and Principe</option><option value="690">Citizen of Seychelles</option><option value="144">Citizen of Sri Lanka</option><option value="659">Citizen of St Christopher (St Kitts) and Nevis</option><option value="140">Citizen of the Central African Republic</option><option value="408">Citizen of the Democratic People's Republic of Korea; Citizen of the DPRK</option><option value="180">Citizen of The Democratic Republic of the Congo</option><option value="214">Citizen of the Dominican Republic</option><option value="384">Citizen of the Ivory Coast</option><option value="178">Citizen of the Republic of the Congo</option><option value="784">Citizen of the United Arab Emirates</option><option value="548">Citizen of Vanuatu</option><option value="166">Cocos (Keeling) Islands</option><option value="170">Colombian</option><option value="174">Comoran</option><option value="184">Cook Islands</option><option value="188">Costa Rican</option><option value="191">Croatian</option><option value="192">Cuban</option><option value="531">Curaçao</option><option value="196">Cypriot</option><option value="203">Czech</option><option value="208">Dane</option><option value="262">Djiboutian</option><option value="212">Dominican</option><option value="528">Dutch citizen; Dutchman; Dutchwoman</option><option value="626">East Timorese</option><option value="218">Ecuadorean</option><option value="818">Egyptian </option><option value="226">Equatorial Guinean</option><option value="232">Eritrean</option><option value="233">Estonian</option><option value="231">Ethiopian</option><option value="238">Falkland Islands (Malvinas)</option><option value="234">Faroe Islands</option><option value="608">Filipino (male), Filipina (female)</option><option value="246">Finn</option><option value="250">French citizen; Frenchman; Frenchwoman</option><option value="254">French Guiana</option><option value="258">French Polynesia</option><option value="260">French Southern Territories</option><option value="266">Gabonese</option><option value="270">Gambian</option><option value="268">Georgian</option><option value="276">German</option><option value="288">Ghanaian</option><option value="292">Gibraltar</option><option value="300">Greek</option><option value="304">Greenland</option><option value="308">Grenadian</option><option value="312">Guadeloupe</option><option value="316">Guam</option><option value="320">Guatemalan</option><option value="831">Guernsey</option><option value="324">Guinean</option><option value="328">Guyanese</option><option value="332">Haitian</option><option value="334">Heard Island and McDonald Islands</option><option value="340">Honduran</option><option value="344">Hong Kong</option><option value="348">Hungarian</option><option value="352">Icelander</option><option value="356">Indian</option><option value="360">Indonesian</option><option value="364">Iranian</option><option value="368">Iraqi</option><option value="833">Isle of Man</option><option value="376">Israeli</option><option value="380">Italian</option><option value="388">Jamaican</option><option value="392">Japanese</option><option value="832">Jersey</option><option value="400">Jordanian</option><option value="398">Kazakh</option><option value="404">Kenyan</option><option value="414">Kuwaiti</option><option value="417">Kyrgyz</option><option value="418">Lao</option><option value="428">Latvian</option><option value="422">Lebanese</option><option value="430">Liberian</option><option value="434">Libyan</option><option value="438">Liechtenstein citizen</option><option value="440">Lithuanian</option><option value="442">Luxembourger</option><option value="446">Macao</option><option value="807">Macedonian</option><option value="454">Malawian</option><option value="462">Maldivian</option><option value="466">Malian</option><option value="470">Maltese</option><option value="584">Marshall Islander</option><option value="474">Martinique</option><option value="478">Mauritanian</option><option value="480">Mauritian</option><option value="175">Mayotte</option><option value="484">Mexican</option><option value="583">Micronesian</option><option value="498">Moldovan</option><option value="492">Monegasque</option><option value="496">Mongolian</option><option value="499">Montenegrin</option><option value="500">Montserrat</option><option value="504">Moroccan</option><option value="508">Mozambican</option><option value="516">Namibian</option><option value="520">Nauruan</option><option value="524">Nepalese</option><option value="540">New Caledonia</option><option value="554">New Zealander</option><option value="558">Nicaraguan</option><option value="566">Nigerian</option><option value="570">Niue</option><option value="574">Norfolk Island</option><option value="580">Northern Mariana Islands</option><option value="578">Norwegian</option><option value="512">Omani</option><option value="586">Pakistani</option><option value="585">Palauan</option><option value="275">Palestine, State of</option><option value="591">Panamanian</option><option value="598">Papua New Guinean</option><option value="600">Paraguayan</option><option value="604">Peruvian</option><option value="612">Pitcairn</option><option value="616">Pole</option><option value="620">Portuguese</option><option value="630">Puerto Rico</option><option value="634">Qatari</option><option value="638">Réunion</option><option value="642">Romanian</option><option value="643">Russian</option><option value="646">Rwandan</option><option value="652">Saint Barthélemy</option><option value="654">Saint Helena, Ascension and Tristan da Cunha</option><option value="663">Saint Martin (French part)</option><option value="666">Saint Pierre and Miquelon</option><option value="222">Salvadorean</option><option value="882">Samoan</option><option value="682">Saudi Arabian</option><option value="686">Senegalese</option><option value="688">Serbian</option><option value="694">Sierra Leonean</option><option value="702">Singaporean</option><option value="534">Sint Maarten (Dutch part)</option><option value="703">Slovak</option><option value="705">Slovene</option><option value="90">Solomon Islander</option><option value="706">Somali</option><option value="710">South African</option><option value="239">South Georgia and the South Sandwich Islands</option><option value="410">South Korean</option><option value="728">South Sudanese</option><option value="724">Spaniard, Spanish citizen</option><option value="662">St Lucian</option><option value="729">Sudanese</option><option value="740">Surinamer</option><option value="744">Svalbard and Jan Mayen</option><option value="748">Swazi</option><option value="752">Swede</option><option value="756">Swiss</option><option value="760">Syrian</option><option value="158">Taiwan, Province of China</option><option value="762">Tajik</option><option value="834">Tanzanian</option><option value="764">Thai</option><option value="768">Togolese</option><option value="772">Tokelau</option><option value="776">Tongan</option><option value="780">Trinidad and Tobago citizen</option><option value="788">Tunisian</option><option value="792">Turk</option><option value="795">Turkmen</option><option value="796">Turks and Caicos Islands</option><option value="798">Tuvaluan</option><option value="800">Ugandan</option><option value="804">Ukrainian</option><option value="840">United States citizen</option><option value="581">United States Minor Outlying Islands</option><option value="858">Uruguayan</option><option value="860">Uzbek</option><option value="336">Vatican citizen</option><option value="862">Venezuelan</option><option value="704">Vietnamese</option><option value="670">Vincentian</option><option value="92">Virgin Islands, British</option><option value="850">Virgin Islands, U.S.</option><option value="876">Wallis and Futuna</option><option value="732">Western Sahara</option><option value="887">Yemeni</option><option value="894">Zambian</option><option value="716">Zimbabwean</option>
                            </select>
                        </div>
                    </div>
                    <div class="control-group" data-bind="validationElement: $data.CODE_DOMICILE_COUNTRY_ID" title="">
                        <label class="control-label">
                            Domicile<sup>*</sup></label>
                        <div class="controls">
                            <select data-bind="AMLDisable: 1, options: BDFactfind._codes.GetCodeTable('CODE_DOMICILE'), optionsText: 'DESCRIPTION', optionsValue: 'ID', value: $data.CODE_DOMICILE_COUNTRY_ID" title="" data-testid="E910A73C-5A06-49EB-A2F2-5FBBA3A75B5C"><option value="4">Afghanistan</option><option value="248">Åland Islands</option><option value="8">Albania</option><option value="12">Algeria</option><option value="16">American Samoa</option><option value="20">Andorra</option><option value="24">Angola</option><option value="660">Anguilla</option><option value="10">Antarctica</option><option value="28">Antigua and Barbuda</option><option value="32">Argentina</option><option value="51">Armenia</option><option value="533">Aruba</option><option value="36">Australia</option><option value="40">Austria</option><option value="31">Azerbaijan</option><option value="44">Bahamas</option><option value="48">Bahrain</option><option value="50">Bangladesh</option><option value="52">Barbados</option><option value="112">Belarus</option><option value="56">Belgium</option><option value="84">Belize</option><option value="204">Benin</option><option value="60">Bermuda</option><option value="64">Bhutan</option><option value="68">Bolivia, Plurinational State of</option><option value="535">Bonaire, Sint Eustatius and Saba</option><option value="70">Bosnia and Herzegovina</option><option value="72">Botswana</option><option value="74">Bouvet Island</option><option value="76">Brazil</option><option value="86">British Indian Ocean Territory</option><option value="96">Brunei Darussalam</option><option value="100">Bulgaria</option><option value="854">Burkina Faso</option><option value="108">Burundi</option><option value="132">Cabo Verde</option><option value="116">Cambodia</option><option value="120">Cameroon</option><option value="124">Canada</option><option value="136">Cayman Islands</option><option value="140">Central African Republic</option><option value="148">Chad</option><option value="152">Chile</option><option value="156">China</option><option value="162">Christmas Island</option><option value="166">Cocos (Keeling) Islands</option><option value="170">Colombia</option><option value="174">Comoros</option><option value="178">Congo</option><option value="180">Congo, the Democratic Republic of the</option><option value="184">Cook Islands</option><option value="188">Costa Rica</option><option value="384">Côte d'Ivoire</option><option value="191">Croatia</option><option value="192">Cuba</option><option value="531">Curaçao</option><option value="196">Cyprus</option><option value="203">Czech Republic</option><option value="208">Denmark</option><option value="262">Djibouti</option><option value="212">Dominica</option><option value="214">Dominican Republic</option><option value="218">Ecuador</option><option value="818">Egypt</option><option value="222">El Salvador</option><option value="226">Equatorial Guinea</option><option value="232">Eritrea</option><option value="233">Estonia</option><option value="231">Ethiopia</option><option value="238">Falkland Islands (Malvinas)</option><option value="234">Faroe Islands</option><option value="242">Fiji</option><option value="246">Finland</option><option value="250">France</option><option value="254">French Guiana</option><option value="258">French Polynesia</option><option value="260">French Southern Territories</option><option value="266">Gabon</option><option value="270">Gambia</option><option value="268">Georgia</option><option value="276">Germany</option><option value="288">Ghana</option><option value="292">Gibraltar</option><option value="300">Greece</option><option value="304">Greenland</option><option value="308">Grenada</option><option value="312">Guadeloupe</option><option value="316">Guam</option><option value="320">Guatemala</option><option value="831">Guernsey</option><option value="324">Guinea</option><option value="624">Guinea-Bissau</option><option value="328">Guyana</option><option value="332">Haiti</option><option value="334">Heard Island and McDonald Islands</option><option value="336">Holy See (Vatican City State)</option><option value="340">Honduras</option><option value="344">Hong Kong</option><option value="348">Hungary</option><option value="352">Iceland</option><option value="356">India</option><option value="360">Indonesia</option><option value="364">Iran, Islamic Republic of</option><option value="368">Iraq</option><option value="372">Ireland</option><option value="833">Isle of Man</option><option value="376">Israel</option><option value="380">Italy</option><option value="388">Jamaica</option><option value="392">Japan</option><option value="832">Jersey</option><option value="400">Jordan</option><option value="398">Kazakhstan</option><option value="404">Kenya</option><option value="296">Kiribati</option><option value="408">Korea, Democratic People's Republic of</option><option value="410">Korea, Republic of</option><option value="414">Kuwait</option><option value="417">Kyrgyzstan</option><option value="418">Lao People's Democratic Republic</option><option value="428">Latvia</option><option value="422">Lebanon</option><option value="426">Lesotho</option><option value="430">Liberia</option><option value="434">Libya</option><option value="438">Liechtenstein</option><option value="440">Lithuania</option><option value="442">Luxembourg</option><option value="446">Macao</option><option value="807">Macedonia, the former Yugoslav Republic of</option><option value="450">Madagascar</option><option value="454">Malawi</option><option value="458">Malaysia</option><option value="462">Maldives</option><option value="466">Mali</option><option value="470">Malta</option><option value="584">Marshall Islands</option><option value="474">Martinique</option><option value="478">Mauritania</option><option value="480">Mauritius</option><option value="175">Mayotte</option><option value="484">Mexico</option><option value="583">Micronesia, Federated States of</option><option value="498">Moldova, Republic of</option><option value="492">Monaco</option><option value="496">Mongolia</option><option value="499">Montenegro</option><option value="500">Montserrat</option><option value="504">Morocco</option><option value="508">Mozambique</option><option value="104">Myanmar</option><option value="516">Namibia</option><option value="520">Nauru</option><option value="524">Nepal</option><option value="528">Netherlands</option><option value="540">New Caledonia</option><option value="554">New Zealand</option><option value="558">Nicaragua</option><option value="562">Niger</option><option value="566">Nigeria</option><option value="570">Niue</option><option value="574">Norfolk Island</option><option value="580">Northern Mariana Islands</option><option value="578">Norway</option><option value="512">Oman</option><option value="586">Pakistan</option><option value="585">Palau</option><option value="275">Palestine, State of</option><option value="591">Panama</option><option value="598">Papua New Guinea</option><option value="600">Paraguay</option><option value="604">Peru</option><option value="608">Philippines</option><option value="612">Pitcairn</option><option value="616">Poland</option><option value="620">Portugal</option><option value="630">Puerto Rico</option><option value="634">Qatar</option><option value="638">Réunion</option><option value="642">Romania</option><option value="643">Russian Federation</option><option value="646">Rwanda</option><option value="652">Saint Barthélemy</option><option value="654">Saint Helena, Ascension and Tristan da Cunha</option><option value="659">Saint Kitts and Nevis</option><option value="662">Saint Lucia</option><option value="663">Saint Martin (French part)</option><option value="666">Saint Pierre and Miquelon</option><option value="670">Saint Vincent and the Grenadines</option><option value="882">Samoa</option><option value="674">San Marino</option><option value="678">Sao Tome and Principe</option><option value="682">Saudi Arabia</option><option value="686">Senegal</option><option value="688">Serbia</option><option value="690">Seychelles</option><option value="694">Sierra Leone</option><option value="702">Singapore</option><option value="534">Sint Maarten (Dutch part)</option><option value="703">Slovakia</option><option value="705">Slovenia</option><option value="90">Solomon Islands</option><option value="706">Somalia</option><option value="710">South Africa</option><option value="239">South Georgia and the South Sandwich Islands</option><option value="728">South Sudan</option><option value="724">Spain</option><option value="144">Sri Lanka</option><option value="729">Sudan</option><option value="740">Suriname</option><option value="744">Svalbard and Jan Mayen</option><option value="748">Swaziland</option><option value="752">Sweden</option><option value="756">Switzerland</option><option value="760">Syrian Arab Republic</option><option value="158">Taiwan, Province of China</option><option value="762">Tajikistan</option><option value="834">Tanzania, United Republic of</option><option value="764">Thailand</option><option value="626">Timor-Leste</option><option value="768">Togo</option><option value="772">Tokelau</option><option value="776">Tonga</option><option value="780">Trinidad and Tobago</option><option value="788">Tunisia</option><option value="792">Turkey</option><option value="795">Turkmenistan</option><option value="796">Turks and Caicos Islands</option><option value="798">Tuvalu</option><option value="800">Uganda</option><option value="804">Ukraine</option><option value="784">United Arab Emirates</option><option value="826">United Kingdom</option><option value="840">United States</option><option value="581">United States Minor Outlying Islands</option><option value="858">Uruguay</option><option value="860">Uzbekistan</option><option value="548">Vanuatu</option><option value="862">Venezuela, Bolivarian Republic of</option><option value="704">Viet Nam</option><option value="92">Virgin Islands, British</option><option value="850">Virgin Islands, U.S.</option><option value="876">Wallis and Futuna</option><option value="732">Western Sahara</option><option value="887">Yemen</option><option value="894">Zambia</option><option value="716">Zimbabwe</option>
                            </select>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </div>
    <div class="span12 wmpformpanel form-horizontal" data-bind="with: $data.Client2, visible: $data.Client2()" style="display: none;"></div>
</div>
<div class="row-fluid">
    <div class="wmpformpanel form-horizontal" data-bind="css: { span12: $root.Client2, span24: !$root.Client2 }, with: $data.Client1">
        <h3>
            Tax Status</h3>
        <div class="row-fluid">
            <div class="span24">
                <div class="centeredDiv">
                    <div class="control-group" data-bind="validationElement: $data.CODE_TAX_RESIDENCY_COUNTRY_ID" title="">
                        <label class="control-label">
                            Residency for tax purposes<sup>*</sup></label>
                        <div class="controls">
                            <select data-bind="AMLDisable: 1, options: BDFactfind._codes.GetCodeTable('CODE_COUNTRY'), optionsText: 'DESCRIPTION', optionsValue: 'ID', value: $data.CODE_TAX_RESIDENCY_COUNTRY_ID" title="" data-testid="916AC0A5-9021-4494-9948-003EA68F2D6B"><option value="4">Afghanistan</option><option value="248">Åland Islands</option><option value="8">Albania</option><option value="12">Algeria</option><option value="16">American Samoa</option><option value="20">Andorra</option><option value="24">Angola</option><option value="660">Anguilla</option><option value="10">Antarctica</option><option value="28">Antigua and Barbuda</option><option value="32">Argentina</option><option value="51">Armenia</option><option value="533">Aruba</option><option value="36">Australia</option><option value="40">Austria</option><option value="31">Azerbaijan</option><option value="44">Bahamas</option><option value="48">Bahrain</option><option value="50">Bangladesh</option><option value="52">Barbados</option><option value="112">Belarus</option><option value="56">Belgium</option><option value="84">Belize</option><option value="204">Benin</option><option value="60">Bermuda</option><option value="64">Bhutan</option><option value="68">Bolivia, Plurinational State of</option><option value="535">Bonaire, Sint Eustatius and Saba</option><option value="70">Bosnia and Herzegovina</option><option value="72">Botswana</option><option value="74">Bouvet Island</option><option value="76">Brazil</option><option value="86">British Indian Ocean Territory</option><option value="96">Brunei Darussalam</option><option value="100">Bulgaria</option><option value="854">Burkina Faso</option><option value="108">Burundi</option><option value="132">Cabo Verde</option><option value="116">Cambodia</option><option value="120">Cameroon</option><option value="124">Canada</option><option value="136">Cayman Islands</option><option value="140">Central African Republic</option><option value="148">Chad</option><option value="152">Chile</option><option value="156">China</option><option value="162">Christmas Island</option><option value="166">Cocos (Keeling) Islands</option><option value="170">Colombia</option><option value="174">Comoros</option><option value="178">Congo</option><option value="180">Congo, the Democratic Republic of the</option><option value="184">Cook Islands</option><option value="188">Costa Rica</option><option value="384">Côte d'Ivoire</option><option value="191">Croatia</option><option value="192">Cuba</option><option value="531">Curaçao</option><option value="196">Cyprus</option><option value="203">Czech Republic</option><option value="208">Denmark</option><option value="262">Djibouti</option><option value="212">Dominica</option><option value="214">Dominican Republic</option><option value="218">Ecuador</option><option value="818">Egypt</option><option value="222">El Salvador</option><option value="226">Equatorial Guinea</option><option value="232">Eritrea</option><option value="233">Estonia</option><option value="231">Ethiopia</option><option value="238">Falkland Islands (Malvinas)</option><option value="234">Faroe Islands</option><option value="242">Fiji</option><option value="246">Finland</option><option value="250">France</option><option value="254">French Guiana</option><option value="258">French Polynesia</option><option value="260">French Southern Territories</option><option value="266">Gabon</option><option value="270">Gambia</option><option value="268">Georgia</option><option value="276">Germany</option><option value="288">Ghana</option><option value="292">Gibraltar</option><option value="300">Greece</option><option value="304">Greenland</option><option value="308">Grenada</option><option value="312">Guadeloupe</option><option value="316">Guam</option><option value="320">Guatemala</option><option value="831">Guernsey</option><option value="324">Guinea</option><option value="624">Guinea-Bissau</option><option value="328">Guyana</option><option value="332">Haiti</option><option value="334">Heard Island and McDonald Islands</option><option value="336">Holy See (Vatican City State)</option><option value="340">Honduras</option><option value="344">Hong Kong</option><option value="348">Hungary</option><option value="352">Iceland</option><option value="356">India</option><option value="360">Indonesia</option><option value="364">Iran, Islamic Republic of</option><option value="368">Iraq</option><option value="372">Ireland</option><option value="833">Isle of Man</option><option value="376">Israel</option><option value="380">Italy</option><option value="388">Jamaica</option><option value="392">Japan</option><option value="832">Jersey</option><option value="400">Jordan</option><option value="398">Kazakhstan</option><option value="404">Kenya</option><option value="296">Kiribati</option><option value="408">Korea, Democratic People's Republic of</option><option value="410">Korea, Republic of</option><option value="414">Kuwait</option><option value="417">Kyrgyzstan</option><option value="418">Lao People's Democratic Republic</option><option value="428">Latvia</option><option value="422">Lebanon</option><option value="426">Lesotho</option><option value="430">Liberia</option><option value="434">Libya</option><option value="438">Liechtenstein</option><option value="440">Lithuania</option><option value="442">Luxembourg</option><option value="446">Macao</option><option value="807">Macedonia, the former Yugoslav Republic of</option><option value="450">Madagascar</option><option value="454">Malawi</option><option value="458">Malaysia</option><option value="462">Maldives</option><option value="466">Mali</option><option value="470">Malta</option><option value="584">Marshall Islands</option><option value="474">Martinique</option><option value="478">Mauritania</option><option value="480">Mauritius</option><option value="175">Mayotte</option><option value="484">Mexico</option><option value="583">Micronesia, Federated States of</option><option value="498">Moldova, Republic of</option><option value="492">Monaco</option><option value="496">Mongolia</option><option value="499">Montenegro</option><option value="500">Montserrat</option><option value="504">Morocco</option><option value="508">Mozambique</option><option value="104">Myanmar</option><option value="516">Namibia</option><option value="520">Nauru</option><option value="524">Nepal</option><option value="528">Netherlands</option><option value="540">New Caledonia</option><option value="554">New Zealand</option><option value="558">Nicaragua</option><option value="562">Niger</option><option value="566">Nigeria</option><option value="570">Niue</option><option value="574">Norfolk Island</option><option value="580">Northern Mariana Islands</option><option value="578">Norway</option><option value="512">Oman</option><option value="586">Pakistan</option><option value="585">Palau</option><option value="275">Palestine, State of</option><option value="591">Panama</option><option value="598">Papua New Guinea</option><option value="600">Paraguay</option><option value="604">Peru</option><option value="608">Philippines</option><option value="612">Pitcairn</option><option value="616">Poland</option><option value="620">Portugal</option><option value="630">Puerto Rico</option><option value="634">Qatar</option><option value="638">Réunion</option><option value="642">Romania</option><option value="643">Russian Federation</option><option value="646">Rwanda</option><option value="652">Saint Barthélemy</option><option value="654">Saint Helena, Ascension and Tristan da Cunha</option><option value="659">Saint Kitts and Nevis</option><option value="662">Saint Lucia</option><option value="663">Saint Martin (French part)</option><option value="666">Saint Pierre and Miquelon</option><option value="670">Saint Vincent and the Grenadines</option><option value="882">Samoa</option><option value="674">San Marino</option><option value="678">Sao Tome and Principe</option><option value="682">Saudi Arabia</option><option value="686">Senegal</option><option value="688">Serbia</option><option value="690">Seychelles</option><option value="694">Sierra Leone</option><option value="702">Singapore</option><option value="534">Sint Maarten (Dutch part)</option><option value="703">Slovakia</option><option value="705">Slovenia</option><option value="90">Solomon Islands</option><option value="706">Somalia</option><option value="710">South Africa</option><option value="239">South Georgia and the South Sandwich Islands</option><option value="728">South Sudan</option><option value="724">Spain</option><option value="144">Sri Lanka</option><option value="729">Sudan</option><option value="740">Suriname</option><option value="744">Svalbard and Jan Mayen</option><option value="748">Swaziland</option><option value="752">Sweden</option><option value="756">Switzerland</option><option value="760">Syrian Arab Republic</option><option value="158">Taiwan, Province of China</option><option value="762">Tajikistan</option><option value="834">Tanzania, United Republic of</option><option value="764">Thailand</option><option value="626">Timor-Leste</option><option value="768">Togo</option><option value="772">Tokelau</option><option value="776">Tonga</option><option value="780">Trinidad and Tobago</option><option value="788">Tunisia</option><option value="792">Turkey</option><option value="795">Turkmenistan</option><option value="796">Turks and Caicos Islands</option><option value="798">Tuvalu</option><option value="800">Uganda</option><option value="804">Ukraine</option><option value="784">United Arab Emirates</option><option value="826">United Kingdom</option><option value="840">United States</option><option value="581">United States Minor Outlying Islands</option><option value="858">Uruguay</option><option value="860">Uzbekistan</option><option value="548">Vanuatu</option><option value="862">Venezuela, Bolivarian Republic of</option><option value="704">Viet Nam</option><option value="92">Virgin Islands, British</option><option value="850">Virgin Islands, U.S.</option><option value="876">Wallis and Futuna</option><option value="732">Western Sahara</option><option value="887">Yemen</option><option value="894">Zambia</option><option value="716">Zimbabwe</option>
                            </select>
                        </div>
                    </div>
                    <div class="control-group">
                        <label class="control-label">
                            Income tax rate</label>
                        <div class="controls">
                            <select data-bind="options: BDFactfind._codes.GetCodeTable('CODE_TAXRATE'), optionsText: 'DESCRIPTION', optionsValue: 'ID', value: $data.CODE_INCOME_TAX_ID" title="" data-testid="75C22531-7651-45D1-8DFE-D5AA335918C8"><option value="0"> </option><option value="1">Non-Tax Payer</option><option value="2">20%</option><option value="3">40%</option><option value="5">45%</option>
                            </select>
                        </div>
                    </div>
                    <div class="control-group" data-bind="validationElement: $data.NINUMBER" title="">
                        <label class="control-label">
                            National Insurance Number</label>
                        <div class="controls">
                            <input type="text" data-bind="value: $data.NINUMBER" title="" data-testid="7EA7EFE5-5697-4049-8926-AD1D7A170512">
                        </div>
                    </div>
                    <div class="control-group">
                        <label class="control-label">
                            Foreign Tax Number</label>
                        <div class="controls">
                            <span>
                                <input type="radio" data-bind="attr: { 'name': $data.CLNT_CLIENT_ID() + '_FOREIGN_TAX_NUMBER' }, checked: $data._computed.FOREIGN_TAX_NUMBER" value="1" name="0A5C601A-4EC5-465F-9358-EEA1F72EC1C3_FOREIGN_TAX_NUMBER" data-testid="D3D3373D-F41C-4D88-94B0-4836E6FAEB81" title="">Yes</span> <span>
                                        <input type="radio" data-bind="attr: { 'name': $data.CLNT_CLIENT_ID() + '_FOREIGN_TAX_NUMBER' }, checked: $data._computed.FOREIGN_TAX_NUMBER" value="0" name="0A5C601A-4EC5-465F-9358-EEA1F72EC1C3_FOREIGN_TAX_NUMBER" data-testid="D6E251D0-62D0-48EB-9DCF-E37EC77CC135" title="">No</span> <span>
                                                <input type="radio" data-bind="attr: { 'name': $data.CLNT_CLIENT_ID() + '_FOREIGN_TAX_NUMBER' }, checked: $data._computed.FOREIGN_TAX_NUMBER" value="2" name="0A5C601A-4EC5-465F-9358-EEA1F72EC1C3_FOREIGN_TAX_NUMBER" data-testid="83B89900-CB3D-4505-BB60-19B25EE3FAF4" title="">Don't Know</span>
                        </div>
                    </div>
                    <div class="control-group" data-bind="visible: $data._computed.FOREIGN_TAX_NUMBER() === '1'" style="display: none;">
                        <label class="control-label">
                            U.S. tax number issued by IRS</label>
                        <div class="controls">
                            <span>
                                <input type="radio" data-bind="attr: { 'name': $data.CLNT_CLIENT_ID() + '_US_TAX_IRS' }, checked: $data._computed.US_TAX_IRS" value="1" name="0A5C601A-4EC5-465F-9358-EEA1F72EC1C3_US_TAX_IRS" data-testid="51AFB4CA-7C08-4773-8214-01DE61C5A027" title="">Yes</span> <span>
                                        <input type="radio" data-bind="attr: { 'name': $data.CLNT_CLIENT_ID() + '_US_TAX_IRS' }, checked: $data._computed.US_TAX_IRS" value="0" name="0A5C601A-4EC5-465F-9358-EEA1F72EC1C3_US_TAX_IRS" data-testid="868E666D-E8C2-4362-887F-9B31E90A52B7" title="">No</span> <span>
                                                <input type="radio" data-bind="attr: { 'name': $data.CLNT_CLIENT_ID() + '_US_TAX_IRS' }, checked: $data._computed.US_TAX_IRS" value="2" name="0A5C601A-4EC5-465F-9358-EEA1F72EC1C3_US_TAX_IRS" data-testid="14DF37EF-6021-40FD-AD47-B7F73818CCFA" title="">Don't Know</span>
                        </div>
                    </div>
                    <div class="control-group" data-bind="visible: $data._computed.US_TAX_IRS() === '1', validationElement: $data.US_TAX_ID_NUMBER" title="" style="display: none;">
                        <label class="control-label">
                            U.S. tax ID number<sup>*</sup></label>
                        <div class="controls">
                            <input type="text" data-bind="value: $data.US_TAX_ID_NUMBER" title="" data-testid="D8C8BBA5-25C2-4B1A-9A2F-24273B220DFB">
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </div>
    <div class="span12 wmpformpanel form-horizontal" data-bind="with: $data.Client2, visible: $data.Client2()" style="display: none;"></div>
</div>
<div class="row-fluid">
    <div class="wmpformpanel form-horizontal" data-bind="css: { span12: $root.Client2, span24: !$root.Client2 }, with: $data.Client1">
        <h3>
            Primary Residence</h3>
        <div class="row-fluid">
            <div class="span24">
                <div class="centeredDiv">
                    <div data-bind="template: { name: 'addressDR', data: $data }"><span class="debugInfo" style="display: none;">addressDR</span><div class="span24">
    <div class="control-group">
        <label class="control-label">
            Country<sup>*</sup></label>
        <div class="controls">
            <select data-bind="AMLDisable: 1, options: BDFactfind._codes.GetCodeTable('CODE_COUNTRY'), optionsText: 'DESCRIPTION', optionsValue: 'ID' , value: $data.CODE_COUNTRY_ID" title="" data-testid="DA5AEB55-FE42-4C92-9D5B-5415763CE66C"><option value="4">Afghanistan</option><option value="248">Åland Islands</option><option value="8">Albania</option><option value="12">Algeria</option><option value="16">American Samoa</option><option value="20">Andorra</option><option value="24">Angola</option><option value="660">Anguilla</option><option value="10">Antarctica</option><option value="28">Antigua and Barbuda</option><option value="32">Argentina</option><option value="51">Armenia</option><option value="533">Aruba</option><option value="36">Australia</option><option value="40">Austria</option><option value="31">Azerbaijan</option><option value="44">Bahamas</option><option value="48">Bahrain</option><option value="50">Bangladesh</option><option value="52">Barbados</option><option value="112">Belarus</option><option value="56">Belgium</option><option value="84">Belize</option><option value="204">Benin</option><option value="60">Bermuda</option><option value="64">Bhutan</option><option value="68">Bolivia, Plurinational State of</option><option value="535">Bonaire, Sint Eustatius and Saba</option><option value="70">Bosnia and Herzegovina</option><option value="72">Botswana</option><option value="74">Bouvet Island</option><option value="76">Brazil</option><option value="86">British Indian Ocean Territory</option><option value="96">Brunei Darussalam</option><option value="100">Bulgaria</option><option value="854">Burkina Faso</option><option value="108">Burundi</option><option value="132">Cabo Verde</option><option value="116">Cambodia</option><option value="120">Cameroon</option><option value="124">Canada</option><option value="136">Cayman Islands</option><option value="140">Central African Republic</option><option value="148">Chad</option><option value="152">Chile</option><option value="156">China</option><option value="162">Christmas Island</option><option value="166">Cocos (Keeling) Islands</option><option value="170">Colombia</option><option value="174">Comoros</option><option value="178">Congo</option><option value="180">Congo, the Democratic Republic of the</option><option value="184">Cook Islands</option><option value="188">Costa Rica</option><option value="384">Côte d'Ivoire</option><option value="191">Croatia</option><option value="192">Cuba</option><option value="531">Curaçao</option><option value="196">Cyprus</option><option value="203">Czech Republic</option><option value="208">Denmark</option><option value="262">Djibouti</option><option value="212">Dominica</option><option value="214">Dominican Republic</option><option value="218">Ecuador</option><option value="818">Egypt</option><option value="222">El Salvador</option><option value="226">Equatorial Guinea</option><option value="232">Eritrea</option><option value="233">Estonia</option><option value="231">Ethiopia</option><option value="238">Falkland Islands (Malvinas)</option><option value="234">Faroe Islands</option><option value="242">Fiji</option><option value="246">Finland</option><option value="250">France</option><option value="254">French Guiana</option><option value="258">French Polynesia</option><option value="260">French Southern Territories</option><option value="266">Gabon</option><option value="270">Gambia</option><option value="268">Georgia</option><option value="276">Germany</option><option value="288">Ghana</option><option value="292">Gibraltar</option><option value="300">Greece</option><option value="304">Greenland</option><option value="308">Grenada</option><option value="312">Guadeloupe</option><option value="316">Guam</option><option value="320">Guatemala</option><option value="831">Guernsey</option><option value="324">Guinea</option><option value="624">Guinea-Bissau</option><option value="328">Guyana</option><option value="332">Haiti</option><option value="334">Heard Island and McDonald Islands</option><option value="336">Holy See (Vatican City State)</option><option value="340">Honduras</option><option value="344">Hong Kong</option><option value="348">Hungary</option><option value="352">Iceland</option><option value="356">India</option><option value="360">Indonesia</option><option value="364">Iran, Islamic Republic of</option><option value="368">Iraq</option><option value="372">Ireland</option><option value="833">Isle of Man</option><option value="376">Israel</option><option value="380">Italy</option><option value="388">Jamaica</option><option value="392">Japan</option><option value="832">Jersey</option><option value="400">Jordan</option><option value="398">Kazakhstan</option><option value="404">Kenya</option><option value="296">Kiribati</option><option value="408">Korea, Democratic People's Republic of</option><option value="410">Korea, Republic of</option><option value="414">Kuwait</option><option value="417">Kyrgyzstan</option><option value="418">Lao People's Democratic Republic</option><option value="428">Latvia</option><option value="422">Lebanon</option><option value="426">Lesotho</option><option value="430">Liberia</option><option value="434">Libya</option><option value="438">Liechtenstein</option><option value="440">Lithuania</option><option value="442">Luxembourg</option><option value="446">Macao</option><option value="807">Macedonia, the former Yugoslav Republic of</option><option value="450">Madagascar</option><option value="454">Malawi</option><option value="458">Malaysia</option><option value="462">Maldives</option><option value="466">Mali</option><option value="470">Malta</option><option value="584">Marshall Islands</option><option value="474">Martinique</option><option value="478">Mauritania</option><option value="480">Mauritius</option><option value="175">Mayotte</option><option value="484">Mexico</option><option value="583">Micronesia, Federated States of</option><option value="498">Moldova, Republic of</option><option value="492">Monaco</option><option value="496">Mongolia</option><option value="499">Montenegro</option><option value="500">Montserrat</option><option value="504">Morocco</option><option value="508">Mozambique</option><option value="104">Myanmar</option><option value="516">Namibia</option><option value="520">Nauru</option><option value="524">Nepal</option><option value="528">Netherlands</option><option value="540">New Caledonia</option><option value="554">New Zealand</option><option value="558">Nicaragua</option><option value="562">Niger</option><option value="566">Nigeria</option><option value="570">Niue</option><option value="574">Norfolk Island</option><option value="580">Northern Mariana Islands</option><option value="578">Norway</option><option value="512">Oman</option><option value="586">Pakistan</option><option value="585">Palau</option><option value="275">Palestine, State of</option><option value="591">Panama</option><option value="598">Papua New Guinea</option><option value="600">Paraguay</option><option value="604">Peru</option><option value="608">Philippines</option><option value="612">Pitcairn</option><option value="616">Poland</option><option value="620">Portugal</option><option value="630">Puerto Rico</option><option value="634">Qatar</option><option value="638">Réunion</option><option value="642">Romania</option><option value="643">Russian Federation</option><option value="646">Rwanda</option><option value="652">Saint Barthélemy</option><option value="654">Saint Helena, Ascension and Tristan da Cunha</option><option value="659">Saint Kitts and Nevis</option><option value="662">Saint Lucia</option><option value="663">Saint Martin (French part)</option><option value="666">Saint Pierre and Miquelon</option><option value="670">Saint Vincent and the Grenadines</option><option value="882">Samoa</option><option value="674">San Marino</option><option value="678">Sao Tome and Principe</option><option value="682">Saudi Arabia</option><option value="686">Senegal</option><option value="688">Serbia</option><option value="690">Seychelles</option><option value="694">Sierra Leone</option><option value="702">Singapore</option><option value="534">Sint Maarten (Dutch part)</option><option value="703">Slovakia</option><option value="705">Slovenia</option><option value="90">Solomon Islands</option><option value="706">Somalia</option><option value="710">South Africa</option><option value="239">South Georgia and the South Sandwich Islands</option><option value="728">South Sudan</option><option value="724">Spain</option><option value="144">Sri Lanka</option><option value="729">Sudan</option><option value="740">Suriname</option><option value="744">Svalbard and Jan Mayen</option><option value="748">Swaziland</option><option value="752">Sweden</option><option value="756">Switzerland</option><option value="760">Syrian Arab Republic</option><option value="158">Taiwan, Province of China</option><option value="762">Tajikistan</option><option value="834">Tanzania, United Republic of</option><option value="764">Thailand</option><option value="626">Timor-Leste</option><option value="768">Togo</option><option value="772">Tokelau</option><option value="776">Tonga</option><option value="780">Trinidad and Tobago</option><option value="788">Tunisia</option><option value="792">Turkey</option><option value="795">Turkmenistan</option><option value="796">Turks and Caicos Islands</option><option value="798">Tuvalu</option><option value="800">Uganda</option><option value="804">Ukraine</option><option value="784">United Arab Emirates</option><option value="826">United Kingdom</option><option value="840">United States</option><option value="581">United States Minor Outlying Islands</option><option value="858">Uruguay</option><option value="860">Uzbekistan</option><option value="548">Vanuatu</option><option value="862">Venezuela, Bolivarian Republic of</option><option value="704">Viet Nam</option><option value="92">Virgin Islands, British</option><option value="850">Virgin Islands, U.S.</option><option value="876">Wallis and Futuna</option><option value="732">Western Sahara</option><option value="887">Yemen</option><option value="894">Zambia</option><option value="716">Zimbabwe</option>
            </select>
        </div>
    </div>

<div data-bind="visible: $data._view.viewMode() === null">
    <div class="span24">
        <div class="control-group error">
            <label class="control-label manualErrorLabel" data-bind="css: { manualErrorLabel: !$data.HOMEPOSTCODE.isValid() }">
                Postcode<sup>*</sup></label>
            <div class="controls">
                <div class="input-append">
                    <input type="text" class="input-small error manualError" data-bind="value: $data.HOMEPOSTCODE, valueUpdate:'input', css: { manualError: !$data.HOMEPOSTCODE.isValid() }" title="Postcode is required and must be valid" data-orig-title="" data-testid="2F175C28-5F8A-490F-AE5D-66E00F360CA8">
                    <span class="add-on hover-pointer" style="margin-left: -3px !important; display: none;" data-bind="visible: $data.CODE_COUNTRY_ID() == '826' &amp;&amp; $data.HOMEPOSTCODE.isValid()">
                        <i class="icon-search" data-bind="click: $data._methods.Lookup, enable: $data.HOMEPOSTCODE">
                        </i></span><span class="add-on  hover-pointer" style="margin-left: 0px !important;">
                            <i class="icon-edit" data-bind="click: $data._methods.EnterManually"></i>
                    </span>
                </div>
            </div>
        </div>
    </div>
</div>
<div data-bind="visible: $data._view.viewMode() === 'manual'" style="display: none;">
    <div class="span24">
        <div class="control-group" data-bind="validationElement: $data.HOMEADDLINE1" title="">
            <label class="control-label">
                Address Line 1<sup>*</sup></label>
            <div class="controls">
                <input type="text" data-bind="AMLDisable: 1, value: $data.HOMEADDLINE1" title="" data-testid="94F95F0D-D8CC-43C7-B7D9-7C85EDB4BB22">
            </div>
        </div>
        
        <div class="control-group">
            <label class="control-label">
                Address Line 2</label>
            <div class="controls">
                <input type="text" data-bind="value: $data.HOMEADDLINE2" title="" data-testid="7E955D87-1812-4C0D-91F2-1D49C8E30DAD">
            </div>
        </div>
        <div class="control-group">
            <label class="control-label">
                Address Line 3</label>
            <div class="controls">
                <input type="text" data-bind="value: $data.HOMEADDLINE3" title="" data-testid="695A963E-0B4D-4E53-BBBF-2C51CE5413A8">
            </div>
        </div>
        <div class="control-group">
            <label class="control-label">
                Address Line 4</label>
            <div class="controls">
                <input type="text" data-bind="value: $data.HOMEADDLINE4" title="" data-testid="62CF3930-B877-4808-AE94-174ADA22C0EA">
            </div>
        </div>
        <div class="control-group" data-bind="validationElement: $data.HOMEADDTOWN" title="">
            <label class="control-label">
                Town<sup>*</sup></label>
            <div class="controls">
                <input type="text" data-bind="AMLDisable: 1, value: $data.HOMEADDTOWN" title="" data-testid="31090C9D-E6DE-466C-AC85-3BE7BDE78E3B">
            </div>
        </div>
        <div class="control-group">
            <label class="control-label">
                County</label>
            <div class="controls">
                <input type="text" data-bind="AMLDisable: 1, value: $data.HOMEADDCOUNTY" title="" data-testid="C90D8E37-AC40-4D1E-B6C8-E9B990701043">
            </div>
        </div>
        <div class="control-group error" data-bind="validationElement: $data.HOMEPOSTCODE" title="Postcode is required and must be valid" data-orig-title="">
            <label class="control-label">
                Postcode<sup>*</sup></label>
            <div class="controls">
                <div class="input-append">
                    <input type="text" class="input-small error" data-bind="AMLDisable: 1, value: $data.HOMEPOSTCODE, valueUpdate: 'afterkeydown'" title="Postcode is required and must be valid" data-orig-title="" data-testid="AC1E9137-5137-4FDA-82F7-A2B682B59EB5">
                    <span class="add-on hover-pointer" style="margin-left: -3px !important; display: none;" data-bind="visible: $data.CODE_COUNTRY_ID() == '826' &amp;&amp; $data.HOMEPOSTCODE.isValid()">
                        <i class="icon-search" data-bind="click: $data._methods.Lookup, enable: $data.HOMEPOSTCODE">
                        </i></span>
                </div>
            </div>
        </div>

        <!-- ko ifnot: $data._TPType() == 'BD_CLNT_CLIENT_DETAIL' --><!-- /ko -->
        <!-- ko if: $data._TPType() == 'BD_CLNT_CLIENT_DETAIL' -->
        <button class="btn btn-small btn-primary" data-bind="click: $root._methods.CopyToOtherClient.bind($data, $data), visible: $root._methods.ShowCopyButton($data), text: 'Copy To Other Client'" style="display: none;">Copy To Other Client</button>
        <!-- /ko -->

    </div>
</div>
<div data-bind="visible: $data._view.viewMode() === 'lookupResults'" style="display: none;">
    <div class="span24">
        <div class="control-group">
            <label class="control-label">
                Results</label>
            <div class="controls">
                <select class="input-block-level no-wrap" size="6" data-bind="options: $data._view.lookupAddresses, optionsText: 'AddressFormatted',  value: $data._view.lookupSelectedAddress" style="word-break: normal;" title="" data-testid="F2C07585-2468-429C-AECE-17730650483E">
                </select>
            </div>
        </div>
        <div class="control-group">
            <label class="control-label">
            </label>
            <div class="controls align-right">
                <button data-bind="click: $data._methods.Lookup_Cancel" class="btn btn-small">
                    Cancel</button>
                <button data-bind="click: $data._methods.Lookup_UseSelected, enable: $data._view.lookupSelectedAddress" class="btn btn-primary btn-small" disabled="">
                    Use Selected</button>
            </div>
        </div>
    </div>
</div>
</div></div>
                    <div class="control-group">
                        <label class="control-label">
                            Residential Status</label>
                        <div class="controls">
                            <select class="input-medium" data-bind="options: BDFactfind._codes.GetCodeTable('CODE_RESIDENTIAL_STATUS'), optionsText: 'DESCRIPTION', optionsValue: 'ID', value: $data.CODE_RESIDENTIAL_STATUS_ID" title="" data-testid="D3FA7B7E-AE3E-4C0E-9835-B3432954B9C1"><option value="1">Owner</option><option value="2">Tenant</option><option value="3">Living with Parents</option><option value="4">Living with Relatives</option><option value="5">Living with Friends</option>
                            </select>
                        </div>
                    </div>
                </div>
            </div>
        </div>
        <h3>
            Additional Addresses</h3>
        <div class="row-fluid">
            <div class="span24">
                <div class="centeredDiv">
                    <div class="control-group" data-bind="if: false"></div>
                    <div data-bind="if: false"></div>

                    <div class="control-group">
                        <label class="control-label">
                            Additional correspondence address?</label>
                        <div class="controls">
                            <span>
                                <input type="radio" data-bind="AMLDisable: 1, attr: { 'name': $data.CLNT_CLIENT_ID() + '_AdditionalCorrespondenceAddresses' }, checked: $data._computed.AdditionalCorrespondenceAddresses" value="1" name="0A5C601A-4EC5-465F-9358-EEA1F72EC1C3_AdditionalCorrespondenceAddresses" data-testid="B2059849-C30D-4857-B209-CC9B33EA0FF0" title="">Yes</span> <span>
                                        <input type="radio" data-bind="AMLDisable: 1, attr: { 'name': $data.CLNT_CLIENT_ID() + '_AdditionalCorrespondenceAddresses' }, checked: $data._computed.AdditionalCorrespondenceAddresses" value="0" name="0A5C601A-4EC5-465F-9358-EEA1F72EC1C3_AdditionalCorrespondenceAddresses" data-testid="4EDFB485-CD5E-4C4E-B2A5-EFC3E7D6F0DE" title="">No</span>
                        </div>
                    </div>
                    <div data-bind="with: $data.BD_CLNT_CLIENT_CORRESPONDENCE_ADDRESS, visible: $data.BD_CLNT_CLIENT_CORRESPONDENCE_ADDRESS().length > 0" style="display: none;">
                        <div data-bind="template: 'correspondenceAddressTable'"><div id="grd" class="expansive clickable">
    <div class="grdHeader">
        <div class="row-fluid hidden-phone">
            <div class="span15">
                Address Line 1</div>
            <div class="span5">
                Post Code</div>
            <div class="span4">
                &nbsp;</div>
        </div>
    </div>
    <!-- ko foreach: $data --><!-- /ko -->
</div>
<div>
    <div class="control-group">
        <label class="control-label">
        </label>
        <div class="controls align-right">
            <div class="input-append">
                <a class="btn btn-small btn-primary" data-bind="click: $parents[0]._methods.BD_CLNT_CLIENT_CORRESPONDENCE_ADDRESS_Add">Add Another</a>
            </div>
        </div>
    </div>
</div>
</div>
                    </div>
                </div>
            </div>
        </div>
    </div>
    <div class="span12 wmpformpanel form-horizontal" data-bind="with: $data.Client2, visible: $data.Client2()" style="display: none;"></div>
</div>

<div class="row-fluid">
    <div class="wmpformpanel form-horizontal" data-bind="css: { span12: $root.Client2, span24: !$root.Client2 }, with: $data.Client1">
        <h3>
            Contact Details</h3>
            <div class="row-fluid">
                <div data-bind="with: $data._computed.BD_CLNT_CLIENT_TELEPHONE_NUMBER_SORTED">
                    <!--<div data-bind="template: {name: 'telephone', data: $data.TelephoneNumbers }"></div>-->
                    <div data-bind="template: 'telephoneTable'"><div id="grd" class="expansive clickable">
    
    <div class="grdHeader">
        <div class="row-fluid hidden-phone">
            <div class="span4">
                Preferred</div>
            <div class="span15">
                Telephone Number</div>
            <div class="span3">
                Type</div>
            <div class="span2">
                &nbsp;</div>
        </div>
    </div>

    <!-- ko foreach: $data --><!-- /ko -->
    <div class="grdRow_Empty" data-bind="visible: $data.length == 0">
        There are no records to display.
    </div>
</div>
<div>
    <div class="control-group">
        <label class="control-label">
        </label>
        <div class="controls align-right">
            <div class="input-append">
                <a class="btn btn-small btn-primary" data-bind="click: $parents[0]._methods.BD_CLNT_CLIENT_TELEPHONE_NUMBER_Add"> Add Another</a>
            </div>
        </div>
    </div>
</div></div>
                </div>
            </div>
            <div class="row-fluid">
                <div data-bind="with: $data._computed.BD_CLNT_CLIENT_EMAIL_ADDRESS_SORTED">
                    <div data-bind="template: 'emailTable'"><div id="grd" class="expansive clickable">
    
    <div class="grdHeader">
        <div class="row-fluid hidden-phone">
            <div class="span4">
                Preferred</div>
            <div class="span14">
                Email Address</div>
            <div class="span4">
                Type</div>
            <div class="span2">
                &nbsp;</div>
        </div>
    </div>

    <!-- ko foreach: $data --><!-- /ko -->
    <div class="grdRow_Empty" data-bind="visible: $data.length == 0">
        There are no records to display.
    </div>
</div>
<div>
    <div class="control-group">
        <label class="control-label">
        </label>
        <div class="controls align-right">
            <div class="input-append">
                <a class="btn btn-small btn-primary" data-bind="click: $parents[0]._methods.BD_CLNT_CLIENT_EMAIL_ADDRESS_Add"> Add Another</a>
            </div>
        </div>
    </div>
</div></div>
                </div>
            </div>
    </div>
    <div class="span12 wmpformpanel form-horizontal" data-bind="with: $data.Client2, visible: $data.Client2()" style="display: none;"></div>
</div>

<div class="row-fluid">
    <div class="wmpformpanel form-horizontal" data-bind="css: { span12: $root.Client2, span24: !$root.Client2 }, with: $data.Client1">
        <h3>
            FCA client classification</h3>
        <div class="row-fluid">
            <div class="span24">
                <div class="centeredDiv">
                    <div class="control-group">
                        <label class="control-label">
                            Client classification</label>
                        <div class="controls">
                            <select data-bind="AMLDisable: 1, options: BDFactfind._codes.GetCodeTable('CODE_FCA_CLIENT_CLASSIFICATION'), optionsText: 'DESCRIPTION', optionsValue: 'ID', value: $data.CODE_FCA_CLIENT_CLASSIFICATION_ID" title="" data-testid="47B2936E-881C-4B3E-8745-5C780666335F"><option value="1">Retail Client</option><option value="2">Professional (Per Se)</option><option value="3">Professional (Elective)</option><option value="4">Eligible Counterparty (Per Se)</option><option value="5">Eligible Counterparty (Elective)</option>
                            </select>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </div>

    <div class="span12 wmpformpanel form-horizontal" data-bind="with: $data.Client2, visible: $data.Client2()" style="display: none;"></div>

</div>
</div>
