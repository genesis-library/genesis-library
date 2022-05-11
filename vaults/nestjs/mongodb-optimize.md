https://itnext.io/performance-tips-for-mongodb-mongoose-190732a5d382

Yaşanan sorun: (düzeldi, saçmalamışım)
```
@Schema()  
export class Category {  
  @Prop({ _id: true })  
  _id: number;  
  @Prop()  
  name: string;  
  
  @Prop()  
  image: string;  
  
  @Prop({ type: [ActivitySchema] })  
  activities: Activity[];  
}

// category.service.ts
@InjectModel(Topic.name)  
private topicModel: Model<TopicDocument>,

const topics: Topic[] = await this.topicModel.find({ _id: topicId }).lean();
bu sorguda içteki objenin idsi gelmiyordu.
lean() ile geldi.

```

LEAN:
Improves query performance by returning plain JSON objects instead of Mongoose docs.
POJO: Plain old javascript object
Documents are heavier than POJO because of internal state for change tracking.

This costs:
- Change Tracking
- Casting and validation
- Getters and setters
- Virtuals
- save() function

use it for get() endpoints.



https://www.getrevue.co/profile/masteringjs/issues/why-you-probably-shouldn-t-use-the-mongodb-aggregation-framework-262215?utm_campaign=Issue&utm_content=view_in_browser&utm_medium=email&utm_source=Mastering+JS+Weekly