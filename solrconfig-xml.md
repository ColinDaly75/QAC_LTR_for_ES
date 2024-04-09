

Here is how the suggester was implemented using Apache Solr: -

```
   <searchComponent name="suggest" class="solr.SuggestComponent">
   <lst name="suggester">
     <str name="name">suggester_all</str>  <!--combines all sources -->
     <str name="lookupImpl">AnalyzingInfixLookupFactory</str>
     <str name="highlight">false</str>
     <str name="dictionaryImpl">DocumentExpressionDictionaryFactory</str>
     <str name="field">suggestion_term_all</str>
     <int name="rows">10</int>
     <str name="weightExpression">((suggestion_weight_1 * 50.1) + (suggestion_weight_2 *1.2) + (suggestion_weight_3 *1.3)  + (suggestion_weight_4 / 14000) + (suggestion_weight_5 * 1) + (suggestion_weight_6 * 300)+ (suggestion_weight_7 * 1))</str>
             <!--<str name="weightExpression">((suggestion_weight_4 +6000) + (suggestion_weight_1 * 1.1) + (suggestion_weight_2 *1.2)  + (suggestion_weight_3 *1.3))</str> -->
     <str name="sortField">suggestion_weight_1</str>
     <str name="sortField">suggestion_weight_2</str>
     <str name="sortField">suggestion_weight_3</str>
     <str name="sortField">suggestion_weight_4</str>
     <str name="sortField">suggestion_weight_5</str>
     <str name="sortField">suggestion_weight_6</str>
     <str name="sortField">suggestion_weight_7</str>
     <str name="suggestAnalyzerFieldType">text_en</str>
     <str name="buildOnStartup">true</str>
   </lst>
  </searchComponent>
  ```


