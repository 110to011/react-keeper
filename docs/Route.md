# Route
## Path
## Component
  * normal component
  * dynamic component 
## Index Component
  * Add `'rc-index'` property to Route component, when path is equals to parent component's path,this one will match and mount.
  ```
  <Route component={ User } path='/user'>
    <Route rc-index component={ Info } path='/info'/>
    <Route component={ Edit } path='/edit'/>
    <Route component={ Article } path='/user'/>
   </Route>
  ```
   *`'rc-indexv` component can no use `'path'` property*
## Miss Match Deal
  * When no component is matched, we should show users something, such as `404` page. we support two way for this scene.
  - use `'rc-miss'` property
  ```
   <Route component={ User } path='/user'>
     <Route component={ Edit } path='/edit'/>
     <Route component={ Article } path='/user'/>
     <Route component={ NotFound } rc-miss/>
   </Route>
  ```
  *`'rc-miss'` component can no use `'path'` property*

  - use `'*'` path property, and add it as the last child
  ```
   <Route component={ User } path='/user'>
     <Route component={ Edit } path='/edit'/>
     <Route component={ Article } path='/user'/>
     <Route component={ NotFound } path='*'/>
   </Route>
  ```
## Blocked Pages