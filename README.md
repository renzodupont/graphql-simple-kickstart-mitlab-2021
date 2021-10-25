# graphql-simple-kickstart-mitlab-2021

Simple project to understand how to implement and use GraphQL easily

# Test Queries:

<h3>Get Restaurants:</h3>

<!-- prettier-ignore -->
{restaurants {
  id
  name
  description
  dishes {
    name
    price
  }
}}

<h3>Get Single Restaurant by Id</h3>

<!-- prettier-ignore -->
{restaurant(id:1) {
  id
  name
  description
  dishes {
    name
    price
  }
}}

<h3>Create Restaurant</h3>

<!-- prettier-ignore -->
mutation setrestaurant($input: restaurantInput) {
  setrestaurant(input: $input) {
    name
    description
    dishes {
      name
      price
    }
  }
}

<!-- prettier-ignore -->
Variables:
{
  "input": {
    "name": "Test",
    "description": "Test"
  }
}

<h3>Edit Restaurant</h3>

<!-- prettier-ignore -->
mutation editrestaurant($id: Int!, $name: String!) {
  editrestaurant(id: $id, name: $name) {
    name
    description
    dishes {
      name
      price
    }
  }
}

<!-- prettier-ignore -->
Variables:
{
  "id": 1,
  "name": "Test Changed"
}

<h3>Delete Restaurant</h3>

<!-- prettier-ignore -->
mutation deleterestaurant($id: Int!) {
  deleterestaurant(id: $id) { 
    ok 
  } 
}

<!-- prettier-ignore -->
Variables:
{
  "id": 1
}
