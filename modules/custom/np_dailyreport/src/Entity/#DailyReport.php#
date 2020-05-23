<?php

namespace Drupal\np_dailyreport\Entity;

use Drupal\Core\Entity\ContentEntityBase;
use Drupal\Core\Field\BaseFieldDefination;
use Drupal\Core\Entity\EntityTypeInterface;
use Drupal\Core\Entity\ContentEntityInterfaace;
use Drupal\Core\Entity\EntityStorageInterface;
use Drupal\Core\Entity\EntityChangedTrait;




/**
 *
 * @ingroup daily_report
 * 
 * Daily Report Content type Defination.
 *
 * @ContentEntityType(
 *   id = "daily_report",
 *   label = @Tranlation("Daily Report"),
 *   handlers = {
 *     "view_builder" = "Drupal\Core\Entity\EntityViewBuilder",
 *     "list_builder" = "Drupal\np_dailyreport\Controller\DailyReportListBuilder",
 *     "form" = {
 *       "default" = "Drupal\np_dailyreport\Form\DailyReportForm",
 *       "delete" = "Drupal\np_dailyreport\Form\DailyReportDeleteForm",
 *     },
 *     "access" = "Drupal\np_dailyreport\DailyReportAccessControlHandler",
 *   },
 *   list_cache_contexts = { "users" },  
 *   base_table = "daily_report",
 *   admin_permission = "administer daily_report entity",
 *   entity_keys = {
 *     id = "id",
 *     label = "title",
 *     uuid = "uuid",
 *   },
 *   links = {
 *     "canonical" = "/daily_report/{daily_report}",
 *     "edit-form" = "/daily_report/{daily_report}/edit",
 *     "delete-form" = "/daily_report/{daily_report}/delete",,
 *     "collection" = "/daily_report/list",
 *   },
 *   field_ui_base_route = "daily_report.daily_report_settings",
 * )
 *
 */

class DailyReport extends ContentEntityBase {
    use EntityChangedTrait;

    public static function baseFieldDefinitions(EntityTypeInterface $entity_type) {

        $fields['id'] = BaseFieldDefinition::create('integer')
            ->setLabel('ID')
            ->setDescription('ID of the DailyReport Entity')
            ->setReadOnly(TRUE);
        $fields['uuid'] = BaseFieldDefinition::create('integer')
            ->setLabel('UUID')
            ->setDescription('The UUID of the DailyReport entity.')
            ->setReadOnly(TRUE);

        $fields['title'] = BaseFieldDefination::create('string')
            ->setLabel('Title')
            ->setDescription('Title of the Dailyreport')
            ->setSettings([
                'max_length' => 255,
                'text_processing' => 0
            ])
            ->setDefaultValue(NULL)
            ->setDisplayOptions('view', [
                'label' => 'above',
                'type' => 'string',
                'weight' => -6,
            ])
            ->setDisplayOPtions('form', [
                'type' => 'string_textfield',
                'weight' => -6
            ])
            ->setDisplayConfigurable('form', TRUE)
            ->setDisplayConfigurable('view', TRUE);
        
        
        $fields['langcode'] = BaseFieldDefinition::create('language')
            ->setLabel(t('Language code'))
            ->setDescription(t('The language code of ContentEntityExample entity.'));
        $fields['created'] = BaseFieldDefinition::create('created')
            ->setLabel(t('Created'))
            ->setDescription(t('The time that the entity was created.'));
        
        $fields['changed'] = BaseFieldDefinition::create('changed')
            ->setLabel(t('Changed'))
            ->setDescription(t('The time that the entity was last edited.'));
        
        return $fields;
    }
}