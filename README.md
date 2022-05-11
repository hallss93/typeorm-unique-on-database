# TyepORM Unique on Database
Validation to avoid duplicate entries in the entity.

## Installation

```
npm i --save typeorm-unique-on-database
```

## Usage

To use it, just import it into your application and use the decorator

```typescript
import { UniqueOnDatabase } from 'typeorm-unique-on-database'; // import

...

@Entity()
export class Company extends BaseEntity {
  @PrimaryGeneratedColumn()
  id: number;

  @Column({ nullable: false })
  @ApiProperty()
  @MinLength(3)
  @UniqueOnDatabase(Company) // pass the entity
  name: string;
  
  ...

}

```