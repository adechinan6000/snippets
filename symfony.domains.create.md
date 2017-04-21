## Entities

```bash
php bin/console doctrine:generate:entity
```

## After adding new properties, generate getters and setters

```bash
php bin/console doctrine:generate:entities AppBundle
```

# Sample Form entities + validation

```php
// src/AppBundle/Entity/Task.php
namespace AppBundle\Entity;

class Task
{
     /**
     * @Assert\NotBlank()
     */
    protected $task;
    
    /**
     * @Assert\NotBlank(message="Fill in please.")
     * @Assert\Type("\DateTime")
     */
    protected $dueDate;

    public function getTask()
    {
        return $this->task;
    }

    public function setTask($task)
    {
        $this->task = $task;
    }

    public function getDueDate()
    {
        return $this->dueDate;
    }

    public function setDueDate(\DateTime $dueDate = null)
    {
        $this->dueDate = $dueDate;
    }
}
```