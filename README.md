SoqlBuilderLite
===============

Slimmed down Soql builder

Example:

SoqlBuilderLite soql = new SoqlBuilderLite()
    .selectx(new Set<String> {
        'Id', 'Name', 'Account.Name'
    })
    .fromx('Opportunity')
    .wherex(new SoqlCondition(
        'OwnerId', Condition.EQUALS, UserInfo.getUserId()
    ))
;

List<Opportunity> opptys = Database.query( soql.toString() );

